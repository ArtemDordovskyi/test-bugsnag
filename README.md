# README

### Describe the bug
I see warnings about circular require every time I run rake tasks.

### Steps to reproduce
1. Create rails application
```
rails new test-bugsnag
cd test-bugsnag
```
2. Update rubygems
```
gem update --system
```
2. Add bugsnag to gems 
```
bundle add bugsnag
```
3. Add `$VERBOSE = true` to `./config/application.rb` config file at the top
```
# ./config/application.rb
require_relative "boot"

$VERBOSE = true

require "rails/all"

# Require the gems listed in Gemfile, including any gems
# you've limited to :test, :development, or :production.
Bundler.require(*Rails.groups)
```
4. Then run command and see warning
```
bundle exec rake -T
```

### Environment
* Bugsnag version: 6.26.3
* Ruby version: 3.2.1
* Bundle version: 2.4.5
* Integration framework version:
    * Rack: 3.0.11
    * Rails: 7.1.3.2
    * Rake: 13.2.1

### Example Repo

- [ ] Create a minimal repository that can reproduce the issue
- [ ] Link to it here:
https://github.com/ArtemDordovskyi/test-bugsnag

<details><summary>Error messages:</summary>

```
/home/user/.rbenv/versions/3.2.1/lib/ruby/gems/3.2.0/gems/bootsnap-1.18.3/lib/bootsnap/load_path_cache/core_ext/kernel_require.rb:30: warning: /home/user/.rbenv/versions/3.2.1/lib/ruby/gems/3.2.0/gems/bootsnap-1.18.3/lib/bootsnap/load_path_cache/core_ext/kernel_require.rb:30: warning: loading in progress, circular require considered harmful - /home/user/.rbenv/versions/3.2.1/lib/ruby/gems/3.2.0/gems/bugsnag-6.26.4/lib/bugsnag.rb
        from /home/user/.rbenv/versions/3.2.1/bin/bundle:25:in  `<main>'
        from /home/user/.rbenv/versions/3.2.1/bin/bundle:25:in  `load'
        from /home/user/.rbenv/versions/3.2.1/lib/ruby/gems/3.2.0/gems/bundler-2.4.5/exe/bundle:33:in  `<top (required)>'
        from /home/user/.rbenv/versions/3.2.1/lib/ruby/gems/3.2.0/gems/bundler-2.4.5/lib/bundler/friendly_errors.rb:117:in  `with_friendly_errors'
        from /home/user/.rbenv/versions/3.2.1/lib/ruby/gems/3.2.0/gems/bundler-2.4.5/exe/bundle:45:in  `block in <top (required)>'
        from /home/user/.rbenv/versions/3.2.1/lib/ruby/gems/3.2.0/gems/bundler-2.4.5/lib/bundler/cli.rb:28:in  `start'
        from /home/user/.rbenv/versions/3.2.1/lib/ruby/gems/3.2.0/gems/bundler-2.4.5/lib/bundler/vendor/thor/lib/thor/base.rb:485:in  `start'
        from /home/user/.rbenv/versions/3.2.1/lib/ruby/gems/3.2.0/gems/bundler-2.4.5/lib/bundler/cli.rb:34:in  `dispatch'
        from /home/user/.rbenv/versions/3.2.1/lib/ruby/gems/3.2.0/gems/bundler-2.4.5/lib/bundler/vendor/thor/lib/thor.rb:392:in  `dispatch'
        from /home/user/.rbenv/versions/3.2.1/lib/ruby/gems/3.2.0/gems/bundler-2.4.5/lib/bundler/vendor/thor/lib/thor/invocation.rb:127:in  `invoke_command'
        from /home/user/.rbenv/versions/3.2.1/lib/ruby/gems/3.2.0/gems/bundler-2.4.5/lib/bundler/vendor/thor/lib/thor/command.rb:27:in  `run'
        from /home/user/.rbenv/versions/3.2.1/lib/ruby/gems/3.2.0/gems/bundler-2.4.5/lib/bundler/cli.rb:491:in  `exec'
        from /home/user/.rbenv/versions/3.2.1/lib/ruby/gems/3.2.0/gems/bundler-2.4.5/lib/bundler/cli/exec.rb:23:in  `run'
        from /home/user/.rbenv/versions/3.2.1/lib/ruby/gems/3.2.0/gems/bundler-2.4.5/lib/bundler/cli/exec.rb:58:in  `kernel_load'
        from /home/user/.rbenv/versions/3.2.1/lib/ruby/gems/3.2.0/gems/bundler-2.4.5/lib/bundler/cli/exec.rb:58:in  `load'
        from /home/user/.rbenv/versions/3.2.1/bin/rake:25:in  `<top (required)>'
        from /home/user/.rbenv/versions/3.2.1/bin/rake:25:in  `load'
        from /home/user/.rbenv/versions/3.2.1/lib/ruby/gems/3.2.0/gems/rake-13.2.1/exe/rake:27:in  `<top (required)>'
        from /home/user/.rbenv/versions/3.2.1/lib/ruby/gems/3.2.0/gems/rake-13.2.1/lib/rake/application.rb:80:in  `run'
        from /home/user/.rbenv/versions/3.2.1/lib/ruby/gems/3.2.0/gems/rake-13.2.1/lib/rake/application.rb:214:in  `standard_exception_handling'
        from /home/user/.rbenv/versions/3.2.1/lib/ruby/gems/3.2.0/gems/rake-13.2.1/lib/rake/application.rb:82:in  `block in run'
        from /home/user/.rbenv/versions/3.2.1/lib/ruby/gems/3.2.0/gems/rake-13.2.1/lib/rake/application.rb:125:in  `load_rakefile'
        from /home/user/.rbenv/versions/3.2.1/lib/ruby/gems/3.2.0/gems/rake-13.2.1/lib/rake/application.rb:214:in  `standard_exception_handling'
        from /home/user/.rbenv/versions/3.2.1/lib/ruby/gems/3.2.0/gems/rake-13.2.1/lib/rake/application.rb:126:in  `block in load_rakefile'
        from /home/user/.rbenv/versions/3.2.1/lib/ruby/gems/3.2.0/gems/rake-13.2.1/lib/rake/application.rb:740:in  `raw_load_rakefile'
        from /home/user/.rbenv/versions/3.2.1/lib/ruby/gems/3.2.0/gems/rake-13.2.1/lib/rake/rake_module.rb:29:in  `load_rakefile'
        from /home/user/.rbenv/versions/3.2.1/lib/ruby/gems/3.2.0/gems/rake-13.2.1/lib/rake/rake_module.rb:29:in  `load'
        from /home/user/projects/test-bugsnag/Rakefile:4:in  `<top (required)>'
        from /home/user/projects/test-bugsnag/Rakefile:4:in  `require_relative'
        from /home/user/projects/test-bugsnag/config/application.rb:9:in  `<top (required)>'
        from /home/user/.rbenv/versions/3.2.1/lib/ruby/gems/3.2.0/gems/bundler-2.4.5/lib/bundler.rb:195:in  `require'
        from /home/user/.rbenv/versions/3.2.1/lib/ruby/gems/3.2.0/gems/bundler-2.4.5/lib/bundler/runtime.rb:44:in  `require'
        from /home/user/.rbenv/versions/3.2.1/lib/ruby/gems/3.2.0/gems/bundler-2.4.5/lib/bundler/runtime.rb:44:in  `each'
        from /home/user/.rbenv/versions/3.2.1/lib/ruby/gems/3.2.0/gems/bundler-2.4.5/lib/bundler/runtime.rb:55:in  `block in require'
        from /home/user/.rbenv/versions/3.2.1/lib/ruby/gems/3.2.0/gems/bundler-2.4.5/lib/bundler/runtime.rb:55:in  `each'
        from /home/user/.rbenv/versions/3.2.1/lib/ruby/gems/3.2.0/gems/bundler-2.4.5/lib/bundler/runtime.rb:60:in  `block (2 levels) in require'
        from /home/user/.rbenv/versions/3.2.1/lib/ruby/gems/3.2.0/gems/zeitwerk-2.6.14/lib/zeitwerk/kernel.rb:34:in  `require'
        from /home/user/.rbenv/versions/3.2.1/lib/ruby/gems/3.2.0/gems/zeitwerk-2.6.14/lib/zeitwerk/kernel.rb:34:in  `require'
        from /home/user/.rbenv/versions/3.2.1/lib/ruby/gems/3.2.0/gems/bugsnag-6.26.4/lib/bugsnag.rb:579:in  `<main>'
        from /home/user/.rbenv/versions/3.2.1/lib/ruby/gems/3.2.0/gems/bugsnag-6.26.4/lib/bugsnag.rb:251:in  `load_integrations'
        from /home/user/.rbenv/versions/3.2.1/lib/ruby/gems/3.2.0/gems/zeitwerk-2.6.14/lib/zeitwerk/kernel.rb:34:in  `require'
        from /home/user/.rbenv/versions/3.2.1/lib/ruby/gems/3.2.0/gems/bootsnap-1.18.3/lib/bootsnap/load_path_cache/core_ext/kernel_require.rb:30:in  `require'
        from /home/user/.rbenv/versions/3.2.1/lib/ruby/gems/3.2.0/gems/bootsnap-1.18.3/lib/bootsnap/load_path_cache/core_ext/kernel_require.rb:30:in  `require'
        from /home/user/.rbenv/versions/3.2.1/lib/ruby/gems/3.2.0/gems/bugsnag-6.26.4/lib/bugsnag/integrations/railtie.rb:5:in  `<main>'
        from /home/user/.rbenv/versions/3.2.1/lib/ruby/gems/3.2.0/gems/zeitwerk-2.6.14/lib/zeitwerk/kernel.rb:34:in  `require'
        from /home/user/.rbenv/versions/3.2.1/lib/ruby/gems/3.2.0/gems/bootsnap-1.18.3/lib/bootsnap/load_path_cache/core_ext/kernel_require.rb:30:in  `require'
        from /home/user/.rbenv/versions/3.2.1/lib/ruby/gems/3.2.0/gems/bootsnap-1.18.3/lib/bootsnap/load_path_cache/core_ext/kernel_require.rb:30:in  `require'
```
</details>
