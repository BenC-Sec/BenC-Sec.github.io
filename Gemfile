source "https://rubygems.org"

# Run the same stack as GitHub Pages. Build/serve locally with:
#   bundle install
#   bundle exec jekyll serve
# To upgrade, run `bundle update github-pages`.
gem "github-pages", "~> 232", group: :jekyll_plugins

# Site plugins (must also be listed under `plugins:` in _config.yml).
group :jekyll_plugins do
  gem "jekyll-feed", "~> 0.12"
  gem "jekyll-remote-theme"   # pulls in the Minimal Mistakes remote theme
  gem "jekyll-include-cache"  # required by Minimal Mistakes (include_cached)
end

# Ruby 3.4 removed several gems from the default stdlib that the pinned
# (older) Jekyll in github-pages still expects. These are only needed for
# LOCAL builds — GitHub Pages runs its own managed toolchain.
gem "webrick", "~> 1.8"
gem "csv"
gem "base64"
gem "bigdecimal"
gem "logger"

# Windows and JRuby do not include zoneinfo files, so bundle tzinfo-data.
platforms :mingw, :x64_mingw, :mswin, :jruby do
  gem "tzinfo", ">= 1", "< 3"
  gem "tzinfo-data"
end

# Performance booster for watching directories on Windows.
gem "wdm", "~> 0.1", :platforms => [:mingw, :x64_mingw, :mswin]

# Lock `http_parser.rb` to v0.6.x on JRuby (newer versions lack a Java counterpart).
gem "http_parser.rb", "~> 0.6.0", :platforms => [:jruby]
