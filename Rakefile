# encoding: utf-8
$:.unshift File.join(File.dirname(__FILE__), 'lib')

require 'bundler'
begin
  Bundler.setup(:default, :development)
rescue Bundler::BundlerError => e
  $stderr.puts e.message
  $stderr.puts "Run `bundle install` to install missing gems"
  exit e.status_code
end
require 'rake'

require 'jeweler'
require 'fakelia'
Jeweler::Tasks.new do |gem|
  # gem is a Gem::Specification... see http://docs.rubygems.org/read/chapter/20 for more options
  gem.name = "fakelia"
  gem.homepage = "http://github.com/seryl/fakelia"
  gem.license = "MIT"
  gem.summary = %Q{one-line summary of your gem}
  gem.description = %Q{longer description of your gem}
  gem.email = "joshtoft@gmail.com"
  gem.authors = ["Josh Toft"]
  gem.version = Fakelia::VERSION
  # dependencies defined in Gemfile
end
Jeweler::RubygemsDotOrgTasks.new

require 'rspec/core'
require 'rspec/core/rake_task'
RSpec::Core::RakeTask.new(:spec) do |spec|
  spec.pattern = FileList['spec/**/*_spec.rb']
end

RSpec::Core::RakeTask.new(:rcov) do |spec|
  spec.pattern = 'spec/**/*_spec.rb'
  spec.rcov = true
end

task :default => :spec

require 'yard'
YARD::Rake::YardocTask.new
