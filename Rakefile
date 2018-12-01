REGION = 'us-east-1'
FUNCTION_NAME = 'arn:aws:lambda:us-east-1:217125206273:function:rubyDemo'

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

desc "Zip project files for deployment"
task :zip do
  `zip -r index.zip . -x@exclude.lst`
end

desc "Upload project files to AWS Lambda"
task :upload do
  `aws lambda --region #{REGION} update-function-code --function-name #{FUNCTION_NAME} --zip-file fileb://index.zip`
end

desc "Deploy project to AWS Lambda, with all prerequisite actions"
task deploy: [:clean, :bundle, :zip, :upload]
