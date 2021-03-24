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
  require_relative './config/environment.rb'
end 

namespace :db do

  desc 'migrate changes to your database'
  task :migrate => :environment do 
    Student.create_table
  end

  desc 'seed database with some dummy data'
  task :seed do
    require_relative './db/seeds.rb'
  end 

end 

#this doesn't actually work, but it allows the tests to pass... if you put it in the db namespace then it does work, as I've done
#not sure what I'm doing wrong exactly.... I also found you can change the test to look for db:console and that works as well to get
#the tests to pass but I'm not sure why I am unable to get it to work as described

#update I figured it out, just needed the environment task also outside of the db namespace
desc 'drop into the pry console'
  task :console => :environment do
    Pry.start
  end

 