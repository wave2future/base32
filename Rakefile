# Copyright (c) 2007-2011 Samuel Tesla

# Permission is hereby granted, free of charge, to any person obtaining a copy
# of this software and associated documentation files (the "Software"), to deal
# in the Software without restriction, including without limitation the rights
# to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
# copies of the Software, and to permit persons to whom the Software is
# furnished to do so, subject to the following conditions:

# The above copyright notice and this permission notice shall be included in
# all copies or substantial portions of the Software.

# THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
# IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
# FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
# AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
# LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
# OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
# THE SOFTWARE.

require File.join(File.dirname(__FILE__), 'config', 'environment.rb')
require 'rake/clean'
require 'rake/gempackagetask'
require 'rake/testtask'
require 'rubygems'

task :default => ['test:all']

gemspec = Gem::Specification.new do |s|
  s.author = "Samuel Tesla"
  s.email = "samuel.tesla@gmail.com"
  s.extra_rdoc_files = ["README"]
  s.files = FileList["Rakefile", "{config,lib,test}/**/*"]
  s.has_rdoc = true
  s.name = 'base32'
  s.require_paths << 'lib'
  s.requirements << 'none'
  s.summary = "Ruby extension for base32 encoding and decoding"
  s.version = "0.2.0"
end

Rake::GemPackageTask.new(gemspec) do |pkg|
  pkg.need_tar = true
end

namespace :test do
  Rake::TestTask.new :all do |t|
    t.libs << 'test'
    t.pattern = 'test/**/*_test.rb'
    t.verbose = true
  end
  Rake::Task['test:all'].comment = 'Run all of the tests'
end
