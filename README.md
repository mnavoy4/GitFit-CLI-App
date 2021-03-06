# GitFit Workout Tracker
___
A great new workout tracking app.

Alt-H Guide
___
  1.  Basic Info
  2.  Demo
  3.  Supporting Technologies
  4.  Install and Setup
  5.  Features
  6.  Status
  7.  Contact
  8.  License

### 1. Basic Info
___
GitFit is a workout tracking app that helps you track your gym sessions and make progress toward your fitness goals. The app is simple and intuitive to help its users stay focused on getting fit. Each user has a unique profile where their gym sessions are logged and their fitness goals cab be updated as they are achieved. 

### 2. Demo
___
Here we can have a video if we make one and also we can just put like some pictures or something

### 3.  Supporting Technologies
___

- Ruby -> 2.6.1
- ActiveRecord -> 6.0
- Sinatra-ActiveRecord -> 2.0
- Rake -> 13.0
- SQLite3 -> 1.4
- tty-prompt
- tty-progressbar
- tty-table

### 4.  Install and Setup
___
To run GitFit clone it from the GitHub repository and install locally.

Run commands:
```
bundle install
rake db:migrate
ruby runner.rb
```

### 5. Features
___

  - Create new Member Profile
  - See Member Profile
  - Edit Member Profile
  - Select Workout
  - Delete Member Profile

  ___
  ``` 
  def self.create_new
    name = self.ask_for_name
    goal = self.ask_for_goal
    Member.create(:name=>name, :goal=>goal)
  end 
  ```
  ```
    def workout
    bar = TTY::ProgressBar.new("Work out in progress [:bar]", total: 30)
    30.times do
      sleep(0.1)
      bar.advance(1)
    end
    puts "Great job! You finished your workout."
  end
  ```
  ```
def display_member_workouts_table
    hash = {}
    workout_array = self.workouts.map(&:body_part)
    workout_array.each { |value| hash[value] ? hash[value] += 1 : hash[value] = 1 }
    table = TTY::Table.new ['Body Part','Workouts Completed'], hash.to_a
    table.render(:ascii)
  end
  ```
  ___

  ###  6.  Status
___

  Current status:  Functional MVP completed
  
  To-do's:

  - [x] fix member sign in 
  - [x] add styling 
  - [ ] complete documentation
  - [ ] make demo video
  - [ ] include descriptions of exercises (maybe with pictures or videos)
  


  ### 7.  Contact
  ___
  GitFit was created by [Michael Navoy](https://www.linkedin.com/in/michael-navoy/), [Brian Gordon](https://github.com/bgordon8), and [Derek Turner](https://www.linkedin.com/in/derek-turner-1354b71b1/).
  
  ### 8. Lisence
  ___
  [Click here to view](https://github.com/ChefBoyRT/TacoLandia/blob/master/License.txt)