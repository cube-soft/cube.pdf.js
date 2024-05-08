require 'rake'

# --------------------------------------------------------------------------- #
# commands
# --------------------------------------------------------------------------- #
DOCKER = 'docker-compose'

# --------------------------------------------------------------------------- #
# default
# --------------------------------------------------------------------------- #
desc "Build without caches and setup docker containers."
task :default => [ :build, :up ]

# --------------------------------------------------------------------------- #
# up
# --------------------------------------------------------------------------- #
desc "Setup docker containers and execute some init scripts."
task :up do
    sh("#{DOCKER} up -d")
    Rake::Task[:status].execute
end

# --------------------------------------------------------------------------- #
# down
# --------------------------------------------------------------------------- #
desc "Teardown docker containers."
task :down do
    sh("#{DOCKER} down")
end

# --------------------------------------------------------------------------- #
# build
# --------------------------------------------------------------------------- #
desc "Build docker containers."
task :build, [:name] do |_, e|
    e.with_defaults(:name => '')
    sh("#{DOCKER} build #{e.name}")
end

# --------------------------------------------------------------------------- #
# build_force
# --------------------------------------------------------------------------- #
desc "Build docker containers without caches."
task :build_force, [:name] do |_, e|
    e.with_defaults(:name => '')
    sh("#{DOCKER} build --no-cache #{e.name}")
end

# --------------------------------------------------------------------------- #
# restart
# --------------------------------------------------------------------------- #
desc "Restart docker containers."
task :restart, [:name] do |_, e|
    e.with_defaults(:name => '')
    sh("#{DOCKER} restart #{e.name}")
    Rake::Task[:status].execute
end

# --------------------------------------------------------------------------- #
# status
# --------------------------------------------------------------------------- #
desc "Show the status of containers."
task :status do
    sh("#{DOCKER} ps")
end
