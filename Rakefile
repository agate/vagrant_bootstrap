task :install do
  puts "[RUNNING]: `bundle install`"
  puts "==========================="
  system("bundle install")

  puts

  puts "[RUNNING]: `bundle bundle exec berks install --path berks_cookbooks`"
  puts "===================================================================="
  system("bundle exec berks install --path berks_cookbooks")
end
