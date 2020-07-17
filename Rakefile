desc 'outputs hello to the terminal'
task :hello do
  puts "hello from Rake!"
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



desc 'drop into the Pry console'
task :console => :environment do
  Pry.start
end



# Run original hello with:     rake hello
# Run 2 namespaced greetings with:  rake greeting:hello   /-or-/  rake greeting:hola
# 1st: Run migration with:     rake db:migrate
# 2nd: Run seed with:     rake db:seed
# 3rd: Run pry with:     rake console
# Test in pry with:     Student.all
