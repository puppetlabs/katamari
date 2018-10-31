# Rakefile for Puppet -*- ruby -*-
begin
  require 'rubygems'
  require 'rubygems/package_task'
rescue LoadError
  # Users of older versions of Rake (0.8.7 for example) will not necessarily
  # have rubygems installed, or the newer rubygems package_task for that
  # matter.
  require 'rake/packagetask'
  require 'rake/gempackagetask'
end

require 'rake'
require 'packaging'
Pkg::Util::RakeUtils.load_packaging_tasks

namespace :package do
  task :bootstrap do
    puts 'Bootstrap is no longer needed, using packaging as a gem.'
  end
  task :implode do
    puts 'Implode is no longer needed, using packaging as a gem.'
  end
end

task :default do
  sh %(rake -T)
end

task :spec do
  sh %(rspec #{ENV['TEST'] || ENV['TESTS'] || 'spec'})
end

desc 'run style analysis with rubocop'
task(:rubocop) do
  require 'rubocop'
  cli = RuboCop::CLI.new
  cli.run(%w(--display-cop-names --format simple))
end
