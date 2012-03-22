# More info at https://github.com/guard/guard#readme

guard 'bundler' do
  watch('Gemfile')
end

guard 'compass' do
  watch(%r{.+\.sass'})
end

guard 'livereload' do
  watch(%r{.+\.(css|js|html)})
end


guard 'rack' do
  watch('Gemfile.lock')
  watch(%r{^(config|lib|app)/.*})
end

