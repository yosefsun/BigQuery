require 'bundler/setup'
require 'bundler/gem_tasks'
require 'rake/testtask'

require 'minitest/autorun'
require 'yaml'
require 'big_query'
require 'pry-byebug'

module BigQuery
  class Client
    attr_accessor :client
  end
end

def config
    return @config if @config
    config_data ||= File.expand_path(File.dirname(__FILE__) + "/.bigquery_settings.yml")
    @config = YAML.load_file(config_data)
end

Rake::TestTask.new(:test) do |test|
  test.libs << 'lib' << 'test'
  test.pattern = 'test/*.rb'
  test.verbose = true
end

task :make_coffee do
	puts File.expand_path(File.dirname(__FILE__) + "/.bigquery_settings.yml")
	@bq = BigQuery::Client.new(config)

	result = @bq.find_or_create_by_field_value('test', 'type', "Task4", "id" => 125, "type" => "Task4")

	puts result

	result = @bq.find_or_create_by_field_value('test', 'type', "Task3", "id" => 125, "type" => "Task3")

	puts result

	result = @bq.find_or_create_by_field_value('test', 'type', "Task3", "id" => 125, "type" => "Task3")

	puts result

	#result = @bq.insert('test' ,"id" => 123, "type" => "Task")

	
end
