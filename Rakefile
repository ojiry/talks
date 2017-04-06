require "pathname"
require "reveal-ck"

desc "Generate reveal.js slides"
task :generate, :dir do |t, args|
  dir = args.dir || ENV["DIR"] || "example"
  generate_args = {
    user_dir: Pathname.new("source").join(dir).to_path,
    gem_dir: RevealCK.path,
    output_dir: Pathname.new("docs").join(dir, "slides").to_path,
    slides_file: Pathname.new("source").join(dir, "slides.md").to_path
  }
  RevealCK::Commands::Generate.new(generate_args).run
end
task(:g, :dir) { |t, arg| Rake::Task[:generate].invoke(arg.dir) }

desc "Start webserver so slides are available via http"
task :server, :dir do |t, args|
  dir = args.dir || ENV["DIR"] || "example"
  serve_args = {
    doc_root: Pathname.new("docs").join(dir, "slides").to_path,
    gem_dir: RevealCK.path,
    output_dir: Pathname.new("docs").join(dir, "slides").to_path,
    port: 10_000,
    host: "localhost",
    slides_file: Pathname.new("source").join(dir, "slides.md").to_path,
    user_dir: Pathname.new("source").join(dir).to_path
  }
  RevealCK::Commands::Serve.new(serve_args).run
end
task(:s, :dir) { |t, arg| Rake::Task[:server].invoke(arg.dir) }
