require 'yaml'

conf = YAML.load File.read './lambdaconfig.yml'

task :default do
  system("rake -T")
end

desc "Clean up temporary files"
task :clean do
  `rm index.zip`
end

desc "Bundle gems for deployment"
task :bundle do
  `bundle install --deployment`
end

desc "Generate version from current commit"
task :generate_version do
  `git rev-parse HEAD > version.txt`
end

desc "Zip project files for deployment"
task zip: [:bundle, :generate_version] do
  `zip -r index.zip . -x@exclude.lst`
end

desc "Upload project files to AWS Lambda"
task :upload do
  `aws lambda --region #{conf["aws_region"]} update-function-code --function-name #{conf["lambda_function_name"]} --zip-file fileb://index.zip`
end

desc "Deploy project to AWS Lambda, with all prerequisite actions"
task deploy: [:clean, :bundle, :generate_version, :zip, :upload]
