require 'rubygems'
require 'compass'
require 'compass/exec'

desc "Generates the HTML project (without all the dev files) and minifies CSS"
task :generate do
  base = File.dirname(__FILE__)
  dest = "#{base}/generated/"

  Compass::Exec::SubCommandUI.new(%w(compile --output-style compressed --force)).run!

  puts "Copying generated files ..."

  FileUtils.rm_r dest
  FileUtils.mkdir dest

  files = Dir.chdir(base) do
    Dir.glob %w' **/*.css **/*.html **/*.js **/*.png **/*.jp*g **/*.gif
      .htaccess humans.txt robots.txt'
  end

  files.each do |file|
    # exclude the icons, that are converted to css sprites
    unless file.match /images\/icons\//
      FileUtils.mkdir_p File.join( dest, File.dirname(file) )
      FileUtils.cp file, File.join( dest, file )
    end

  end

  puts "done"
end
