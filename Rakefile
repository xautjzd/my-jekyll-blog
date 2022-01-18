require 'fileutils'

desc "Creating a new post"
task :new do
  puts "What's the name for your next post?"
  @name = STDIN.gets.chomp
  @slug = @name.downcase.strip.gsub(' ', '-')
  @date = Time.now.strftime("%F")
  @post_name = "_posts/#{@date}-#{@slug}.markdown"
  FileUtils.touch(@post_name)
  open(@post_name, 'a' ) do |file|
    file.puts "---"
    file.puts "layout: post"
    file.puts "title: #{@name}"
    file.puts "categories: "
    file.puts "---"
  end

  system "emacs #{@post_name}"
end
