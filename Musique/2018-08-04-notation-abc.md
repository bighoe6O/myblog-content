Title:  Notation ABC
Date:   2018-08-04 11:38:32 +0200
Slug: musique-notation-abc
Tags: DAW, ABC, Notation


[Documentation](http://abcnotation.com/wiki/abc:standard:v2.2)

<http://www.mit.edu/~6.005/fa12/projects/abcPlayer/>

<http://www.mit.edu/~6.005/fa12/projects/abcPlayer/assignment_files/abc_subset_bnf.txt>

<http://abcnotation.com/>

# Accordeon

<https://m.youtube.com/watch?v=xNaskUU5los#>

Tam Lin

<https://thesession.org/tunes/248>

Session Book

<https://thesession.org/members/105978/tunebook>

## Logiciels

<http://abcnotation.com/software>

[EasyABC](https://www.nilsliberg.se/ksp/easyabc/)

### abc2xml

[abc2xml](https://wim.vree.org/svgParse/abc2xml.html)

<https://wim.vree.org/svgParse/abc2xml.py-218.zip>

### pyabc

<https://github.com/campagnola/pyabc>

### abcm2ps

<https://github.com/leesavide/abcm2ps>

### abc2midi



# Rakefile

```ruby
# Rakefile
require 'rake'
require 'rake/clean'

ABC_FILES = Rake::FileList.new("**/*.abc") do |fl|
  fl.exclude("~*")
  fl.exclude('balk1.abc')
  fl.exclude do |f|
    `git ls-files #{f}`.empty?
  end
end

task :default => :list_abc

task :all => [:midi, :ps, :svg, :html]

task :list_abc do
  # sh "ls *.abc"
  # files = Rake::FileList['*.abc']
  puts ABC_FILES
  puts ABC_FILES.ext('.ps')
end

task :test do
  puts 
end

rule ".ps" => ".abc" do |t|
  puts "abcm2ps -O #{t.name} #{t.source}"
  sh "abcm2ps -O #{t.name} #{t.source}"
end

rule ".svg" => ".abc" do |t|
  puts "abcm2ps -g -O #{t.name} #{t.source}"
  sh "abcm2ps -g -O #{t.name} #{t.source}"
end

rule ".html" => ".abc" do |t|
  puts "abcm2ps -X -O #{t.name} #{t.source}"
  sh "abcm2ps -X -O #{t.name} #{t.source}"
end

rule ".mid" => ".abc" do |t|
  puts "abc2midi -o #{t.name} #{t.source}"
  sh "abc2midi #{t.source} -o #{t.name}"
end

task :ps => ABC_FILES.ext(".ps")
task :midi => ABC_FILES.ext(".mid")
task :html => ABC_FILES.ext(".html")
task :svg => ABC_FILES.ext(".svg")

CLEAN.include(ABC_FILES.ext('.ps'))
CLEAN.include(ABC_FILES.ext('.mid'))
CLEAN.include(ABC_FILES.ext('.svg'))
CLEAN.include(ABC_FILES.ext('.html'))
```
