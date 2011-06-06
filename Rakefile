#
#   Copyright 2010 Ricoh Company, Ltd.
#
#   This file is part of Castoro.
#
#   Castoro is free software: you can redistribute it and/or modify
#   it under the terms of the GNU Lesser General Public License as published by
#   the Free Software Foundation, either version 3 of the License, or
#   (at your option) any later version.
#
#   Castoro is distributed in the hope that it will be useful,
#   but WITHOUT ANY WARRANTY; without even the implied warranty of
#   MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
#   GNU Lesser General Public License for more details.
#
#   You should have received a copy of the GNU Lesser General Public License
#   along with Castoro.  If not, see <http://www.gnu.org/licenses/>.
#

require 'rubygems'
require 'rake'
require 'rake/clean'
require 'rake/gempackagetask'
require 'rake/rdoctask'

spec = Gem::Specification.new do |s|
  s.name = 'ap4r-dispatcher'
  s.version = '0.3.7'
  s.has_rdoc = true
  s.extra_rdoc_files = ['Ap4r-README.txt', 'README.txt', 'MIT-LICENSE']
  s.summary = 'Dispatcher of Asynchronous Processing for Ruby.'
  s.description = 'Dispatcher of Asynchronous Processing for Ruby.'
  s.files = %w(History.txt MIT-LICENSE Ap4r-README.txt README.txt Rakefile) + Dir.glob("{lib,spec}/**/*")
  s.require_path = "lib"

  s.add_dependency('reliable-msg', '=1.1.0')
end

Rake::GemPackageTask.new(spec) do |p|
  p.gem_spec = spec
  p.need_tar = false
  p.need_zip = false
end

Rake::RDocTask.new do |rdoc|
  files =['README.txt', 'MIT-LICENSE', 'lib/**/*.rb']
  rdoc.rdoc_files.add(files)
  rdoc.main = "README.txt"
  rdoc.title = "ap4r-dispatcher Docs"
  rdoc.rdoc_dir = 'doc/rdoc'
  rdoc.options << '--line-numbers'
end

Dir['tasks/**/*.rake'].each { |t| load t }

task :default => [:spec]

