# JJ's Rakefile (for jjbuckley.github.com)
# Converts all Markdown text files to HTML.
require 'erb'
require 'rubygems'
require 'rdiscount'
require 'rake/clean'
require 'nokogiri'

LAYOUT = 'layout.html.erb'

TXT = FileList['**/*.txt']
YML = TXT.ext('yml')
HTML = TXT.ext('html')

CLEAN.include("**/*.html")

rule '.html' => ['.yml', LAYOUT] do |rule|
  y = YAML.load(File.read(rule.source))
  y['html'] = RDiscount.new(y['content']).to_html
  erb = ERB.new(File.read('layout.html.erb'))
  html = erb.result(OpenStruct.new(y).send(:binding))
  File.open(rule.name, 'w') do |f|
    f.print(html)
  end
end

rule '.yml' => '.txt' do |rule|
  text = File.read(rule.source)
  y = File.exists?(rule.name) ? YAML.load(File.read(rule.name)) : {}
  y['title'] ||= File.basename(rule.name, '.yml').split('-').join(' ')
  y['content'] = text
  y['description'] ||= text.split("\n\n")[1].gsub("\n", " ")
  y['author'] ||= ENV['USER']
  File.open(rule.name, 'w') do |f|
    YAML.dump(y, f)
  end
end

desc "Build the HTML pages"
task :build => HTML

task :default => :build
