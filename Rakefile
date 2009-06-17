# Look in the tasks/setup.rb file for the various options that can be
# configured in this Rakefile. The .rake files in the tasks directory
# are where the options are used.

begin
  require 'bones'
  Bones.setup
rescue LoadError
  begin
    load 'tasks/setup.rb'
  rescue LoadError
    raise RuntimeError, '### please install the "bones" gem ###'
  end
end

ensure_in_path 'lib'
require 'hexwrench'

task :default => 'test:run'

PROJ.name = 'hexwrench'
PROJ.authors = 'Eric Monti'
PROJ.email = 'emonti@matasano.com'
PROJ.description = 'A wxwidgets-based hex editor written in ruby'
#PROJ.url = 'hexwrench.rubyforge.org'
PROJ.version = Hexwrench::VERSION
PROJ.rubyforge.name = 'hexwrench'
PROJ.readme_file = 'README.rdoc'

PROJ.spec.opts << '--color'

PROJ.rdoc.opts << '--line-numbers'

#PROJ.rdoc.opts << '--diagram'
PROJ.notes.tags << "X"+"XX" # muhah! so we don't note our-self

# exclude rcov.rb from rcov report
PROJ.rcov.opts += ["--exclude",  "rcov.rb", "--exclude", "eventmachine"]

depend_on 'wxruby', '>= 2.0.0'

# EOF
