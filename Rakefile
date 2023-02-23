#The task is defined by using keyword task and the name of the task as a symbol and code block
desc 'Outputs hello to the terminal'
task :hello do
  puts "hello from Rake!"
end

# It is worth noting that the rake tasks can be namespaced 
# Namespacing is a way to group or contain something. 

desc 'outputs hola to the terminal'
task :hola do 
  puts "hola de Rake!"
end

# WE can namespace hola and hello under greeting
namespace :greeting do
  desc 'Outputs hello to the terminal'
  task :hello do
    puts "hello from Rake!"
  end

  desc 'outputs hola to the terminal'
  task :hola do 
    puts "hola de Rake!"
  end

end


# TO VIEW THE LIST OF TASKS AVAILABLE IN THE RAKE FILE WE CAN USE THE COMMAND rake -T though the task must have a description

# The Rakefile contains the task that needs automation
#The file in itself is defined in teh root directory and the defining of the rake task is easy
task :environment do
  require_relative './config/environment'
end

namespace :db do
  desc 'migrate changes to your database'
  task migrate: :environment do
    Student.create_table
  end

  desc 'seed the database with some dummy data'
  task seed: :environment do
    require_relative './db/seeds'
  end
end

desc 'drop into the Pry console'
task console: :environment do
  Pry.start
end