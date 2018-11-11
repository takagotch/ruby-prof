### ruby-prof
---
https://github.com/ruby-prof/ruby-prof

```
gem install ruby-prof
ruby-prof -h

```

```ruby
require 'ruby-prof'
RubyProf.start
result = RubyProf.stop
printer = RubyProf::FlatPrinter.new(result)
printer.print(STDOUT)

require 'ruby-prof'
result = RubyProf.profile do
end
printer = RubyProf::GraphPrinter.new(result)
printer.print(STDOUT, {})

require 'ruby-prof'
result = RubyProf.profile do
end
printer = RubyProf::GraphPronter.new(result)
printer.print(STDOUT, {})

require 'ruby-prof'
RubyProf.start
RubyProf.pause
RubyProf.resume
result = RubyProf.stop

require 'ruby-prof'
RubyProf.resume do
end
result = RubyProf.stop

result = RubyProf.stop
result.eliminate_methods!([/Integer#times/])

profile = RubyProf::Profile.new(...)
profile.exclude_methods!(Integer, :times, ...)
profile.start

profile.exclude_common_methods!

group :profile do
  gem 'ruby-prof'
end

if Rails.env.profile?
  use Rack::RubyProf, :path => '/temp/profile'
end

result = RubyProf.stop
printer = RubyProf::GraphPrinter.new(result)
printer.print(STDOUT, :min_percent => 2)

printer = RubyProf::MultiPrinter.new(result)
printer.print(:path => ".", :profile => "profile")

RubyProf.measure_mode = RubyProf::WALL_TIME
RubyProf.measure_mode = RubyProf::PROCESS_TIME
RubyProf.measure_mode = RubyProf::CPU_TIME
RubyProf.measure_mode = RubyProf::ALLOCATIONS
RubyProf.measure_mode = RubyProf::MEMORY
RubyProf.measure_mode = RubyProf::GC_TIME
RubyProf.measure_mode = RubyProf::GC_RUNS

export RUBY_PROF_MEASURE_MODE=wall
export RUBY_PROF_MEASURE_MODE=process
export RUBY_PROF_MEASURE_MODE=cpu
export RUBY_PROF_MEASURE_MODE=allocations
export RUBY_PROF_MEASUER_MODE=memory
export RUBY_PROF_MEASURE_MODE=gc_time
export RUBY_PROF_MEASURE_MODE=gc_runs
```

```
```
