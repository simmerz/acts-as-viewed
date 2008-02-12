require 'rubygems'

Gem::manage_gems

require 'rake/rdoctask'
require 'rake/packagetask'
require 'rake/gempackagetask'
require 'rake/testtask'

PKG_NAME           = 'acts_as_viewed'
PKG_VERSION        = '1.0.0'
PKG_FILE_NAME      = "#{PKG_NAME}-#{PKG_VERSION}"
PROD_HOST          = "damianmarti@gmail.com"
RUBY_FORGE_PROJECT = 'acts-as-viewed'
RUBY_FORGE_USER    = 'damianmarti'

desc 'Generate documentation for the acts_as_viewed plugin.'
Rake::RDocTask.new(:rdoc) do |rdoc|
  rdoc.rdoc_dir = 'doc'
  rdoc.title    = "#{PKG_NAME} -- View count system for ActiveRecord models"
  rdoc.options << '--line-numbers'
  rdoc.options << '--inline-source'
  rdoc.rdoc_files.include('README')
  rdoc.rdoc_files.include('lib/**/*.rb')
end

spec = Gem::Specification.new do |s|
  s.name            = PKG_NAME
  s.version         = PKG_VERSION
  s.platform        = Gem::Platform::RUBY
  s.summary         = "View count system for active record models"
  s.files           = FileList["{lib,test}/**/*"].to_a + %w(README MIT-LICENSE)
  s.require_path    = 'lib'
  s.has_rdoc        = true
  s.add_dependency    'activerecord', '>= 1.10.1'
  s.add_dependency    'activesupport', '>= 1.1.1'
  s.author          = "Damian Martinelli"
  s.email           = "damianmarti@gmail.com"
  s.homepage        = "http://www.do2.com.ar"
end

Rake::GemPackageTask.new(spec) do |pkg|
  pkg.need_tar = true
end

