# GemfileUpdaterTool


## Usage







Generate diff of `Gemfile.lock` and Markdown table output

After create pull-request

```
# Generate access token https://github.com/settings/tokens
export OCTOKIT_ACCESS_TOKEN=1234567.....

git clone https://github.com/7coAim/gemfile_updater_tool
cd gemfile_updater_tool

bundle install --path .bundle
```


【ATTENTION】
`.bundle/ruby/2.5.0/gems/compare_linker-1.4.2/lib/compare_linker/lockfile_comparator.rb`
```
_, owner, gem_name = old_spec.source.uri.match(/github\.com\/([^\/]+)\/([^.]+)/).to_a
```
→ Regular expression modified code:
```
/github\.com[:\/]([^\/]+)\/([^.]+)/
```


```
bundle exec ruby ./exe/gemfile_updater_tool --repository owner/repo_name --pull-request XXXX
```
XXXX: PR number


**output**

Markdown 
```Markdown
| gem | diff | check | memo |
| --- | --- | --- | --- |
| committee | [compare](https://github.com/interagent/committee/compare/v2.2.0...v2.2.1) | :sun_with_face: | xxxxx |
| graphql | [compare](https://github.com/rmosolgo/graphql-ruby/compare/v1.8.8...v1.8.10) | :sun_with_face: | xxxxx |
```
↓

| gem | diff | check | memo |
| --- | --- | --- | --- |
| committee | [compare](https://github.com/interagent/committee/compare/v2.2.0...v2.2.1) | :sun_with_face: | xxxxx |
| graphql | [compare](https://github.com/rmosolgo/graphql-ruby/compare/v1.8.8...v1.8.10) | :sun_with_face: | xxxxx |







## Development

After checking out the repo, run `bin/setup` to install dependencies. Then, run `rake spec` to run the tests. You can also run `bin/console` for an interactive prompt that will allow you to experiment.

To install this gem onto your local machine, run `bundle exec rake install`. To release a new version, update the version number in `version.rb`, and then run `bundle exec rake release`, which will create a git tag for the version, push git commits and tags, and push the `.gem` file to [rubygems.org](https://rubygems.org).

## Contributing

Bug reports and pull requests are welcome on GitHub at https://github.com/[USERNAME]/gemfile_updater_tool. This project is intended to be a safe, welcoming space for collaboration, and contributors are expected to adhere to the [Contributor Covenant](http://contributor-covenant.org) code of conduct.

## License

The gem is available as open source under the terms of the [MIT License](https://opensource.org/licenses/MIT).

## Code of Conduct

Everyone interacting in the GemfileUpdaterTool project’s codebases, issue trackers, chat rooms and mailing lists is expected to follow the [code of conduct](https://github.com/[USERNAME]/gemfile_updater_tool/blob/master/CODE_OF_CONDUCT.md).
