task default: %w[build]

task :build do
  `bundle exec jekyll build`
end

task :publish do
  `bundle exec jekyll build`
  `cd _site; git add -A; git commit -m '.'; git push`
end
