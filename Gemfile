source "https://rubygems.org"

# This is the same gem GitHub Pages uses server-side — using it locally
# means what you see on your machine matches what GitHub will actually build.
gem "github-pages", group: :jekyll_plugins

group :jekyll_plugins do
  gem "jekyll-feed"
end

# Windows/JRuby compatibility (harmless to leave in on Mac/Linux)
platforms :mingw, :x64_mingw, :mswin, :jruby do
  gem "tzinfo", ">= 1", "< 3"
  gem "tzinfo-data"
end

gem "wdm", "~> 0.1.1", :platforms => [:mingw, :x64_mingw, :mswin]
