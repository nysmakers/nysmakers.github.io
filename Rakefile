desc "compile and run the site"
task :default do
  pids = [
    spawn("jekyll serve -w"),
    spawn("scss --watch 2014/stylesheets/scss:2014/stylesheets"),
    spawn("coffee -b -w -o javascripts -c javascripts/*.coffee")
  ]

  trap "INT" do
    Process.kill "INT", *pids
    exit 1
  end

  loop do
    sleep 1
  end
end
