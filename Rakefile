# This creates a task dependency. Since our Student.create_table 
# code would require access to the config/environment.rb file 
# (which is where the student class and database are loaded), 
# we need to give our task access to this file. In order to do that, 
# we need to define yet another Rake task that we can tell to run 
# before the migrate task is run
task :environment do
  require_relative './config/environment'
end
 
namespace :db do
  desc 'migrate changes to your database'
  task :migrate => :environment do
    Student.create_table
  end

  desc 'seed the database with some dummy data'
  task :seed do
    require_relative './db/seeds.rb'
  end
end

# We'll define a task that starts up the Pry console. We'll 
# make this task dependent on our environment task so that 
# the Student class and the database connection load first.
desc 'drop into the Pry console'
task :console => :environment do
  Pry.start
end


namespace :greeting do
  desc 'outputs hello to the terminal'
    task :hello do
      puts "hello from Rake!"
    end
   
    desc 'outputs hola to the terminal'
    task :hola do
      puts "hola de Rake!"
    end
  end

  

