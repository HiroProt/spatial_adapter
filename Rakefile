require 'rubygems'
require 'rspec/core/rake_task'

[:mysql, :mysql2, :postgresql].each do |adapter|
  desc "Run specs for #{adapter} adapter"
  RSpec::Core::RakeTask.new("spec:#{adapter.to_s}") do |spec|
    spec.pattern = "spec/#{adapter}/*_spec.rb"
    spec.rspec_opts = ['--backtrace']
  end
end

begin
  require 'jeweler'
  Jeweler::Tasks.new do |gem|
    gem.name = "spatial_adapter"
    gem.summary = "Spatial Adapter for ActiveRecord"
    gem.description = "Provides enhancements to ActiveRecord to handle spatial datatypes in PostgreSQL and MySQL."
    gem.authors = ["Pete Deffendol", "Guilhem Vellut"]
    gem.email = "pete@fragility.us"
    gem.homepage = "http://github.com/fragility/spatial_adapter"
    
    gem.files = FileList[
      "rails/*.rb",
      "lib/**/*.rb",
      "MIT-LICENSE",
      "README.rdoc",
      "VERSION"
    ]
    gem.test_files = FileList[
      "spec/**/*.rb",
      "spec/README.txt"
    ]
  
    gem.add_dependency 'activerecord', '>= 2.2.2'
    gem.add_dependency 'GeoRuby', '>= 1.3.0'
  end

  Jeweler::GemcutterTasks.new
rescue LoadError
  puts "WARNING: Jeweler is not available for building packages. Install it with: gem install jeweler"
end
