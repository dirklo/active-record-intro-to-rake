namespace :greeting do
  desc 'outputs hello to the terminal'
  task :hello do
    puts "hello from Rake!"
  end

  task :hola do
    puts "hola de Rake!" 
  end
end

desc 'starts the console'
task :console do
  Pry.start
end

namespace :db do
  desc 'migrates your db info'
  task :migrate => :environment do
    sql = <<-SQL
      CREATE TABLE IF NOT EXISTS students (id, name, grade);
    SQL
    DB[:conn].execute(sql)
  end
  
  task :environment do
    require_relative './config/environment.rb'
  end

  task :seed do
    require_relative './db/seeds.rb'
  end

end
