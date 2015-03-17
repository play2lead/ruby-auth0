#!/usr/bin/env rake
require "bundler/gem_tasks"

begin
	require 'rspec/core/rake_task'

	desc "Run Integration Tests"
	RSpec::Core::RakeTask.new(:integration) do |t|
		t.pattern = FileList["spec/integration/**/*#{ENV['PATTERN']}*_spec.rb"]
	end


	desc "Run Unit Tests"
	RSpec::Core::RakeTask.new(:spec) do |t|
		t.pattern = FileList["spec/lib/auth0/**/*#{ENV['PATTERN']}*_spec.rb"]
	end

	task :default => :spec

	task :all => [:spec, :integration]
rescue LoadError
	#No RSpec
end