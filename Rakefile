require "bundler"
Bundler.setup

require "rspec/core/rake_task"
Rspec::Core::RakeTask.new(:spec)

gemspec = eval(File.read("humanizer.gemspec"))

task :build => "#{gemspec.full_name}.gem"

file "#{gemspec.full_name}.gem" => gemspec.files + ["humanizer.gemspec"] do
  system "gem build humanizer.gemspec"
  system "gem install humanizer-#{NewGem::VERSION}.gem"
end