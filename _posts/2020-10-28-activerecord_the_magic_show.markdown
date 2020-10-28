---
layout: post
title:      "ActiveRecord, The Magic Show"
date:       2020-10-28 19:12:12 +0000
permalink:  activerecord_the_magic_show
---


**What goes on behind the scenes!**

As I have progessed through this challenging gauntlet of modules, I like to envision myself sitting up in the production studio, now. Where as before, I spent all of my time behind the scenes, involved with every minor detail, that the magic show had to offer. Working back there was lot of hard work, that involved a lot of (what seemed unnecessary) code. And, there were days when doubt would creep into the picture, but I kept telling myself "The show must go on!" And it did!

While working behind the scenes, I can promise you, that there was a ton of moving parts for me to be aware of and comprehend. And, for a period of time, I felt like I wasn't going to understand most of them. But, slowly and surely, I began to acclimate myself to one of the new data types, or methods that was associated each day. And, it was through the everyday struggle of keeping the show alive, that I gained confidence in myself to continue. After all, without going through those struggles, my foundation for understanding these concepts would have crumbled.

Now, today, I feel as if I'm sitting comfortably up in the production studio just calling the shots. And, I can't say enough good things about Active Record and the magic it possesses.

Creating Tables:

Active Record completely simplifies the entire process of creating tables, as it takes care of all the tricky SQL statements for you, and instead of writing something like this, everytime I want to create a table:

```
class Dog
....
    def self.create_table
        sql = <<-SQL
        CREATE TABLE IF NOT EXISTS dogs (
            id INTEGER PRIMARY KEY,
            name TEXT,
            breed TEXT
        )
        SQL

        DB[:conn].execute(sql)
    end
```

All I have to do, now, with Active Record is: 

```
class CreateNetworks < ActiveRecord::Migration[5.1]
  def change
    create_table :networks do |t| 
      t.string :call_letters
      t.integer :channel
    end
  end
end
```

Now, the major difference and takeaway, from the introduction of Active Record, is the folder and file construction/placement. Which, ultimately, is key for Active Record to do it's thing. But, it's so much faster to complete, and easier to syntactically remember. Not to mention, everything in the program seems to look in order, and it's easier to manage what is going on where, instead of all the code being in one file.

Migrations:

Before Active Record came into the picture, migrations were tricky to keep up with. Like I said previously, all of the code was compiled into one file, and I never really could visually understand when code was migrating to my table. Nonetheless, everytime I wanted to update a column or remove a column, I would have to create a new method and write some more tricky SQL statements. With the introduction to Active Record, it has eased away those pains, and at the same time has allowed me to visually comprehend what is actually going on, and where it is happening. So long, as I construct the correct folders, and place my files in the right place with the correct file names, completing these migrations seems, now, like a walk in the park. After all, Active Record handles all of the tricky SQL statements, that I had to write out before!

Associations:

Writing object oriented code is all about associations, and without them, our program (code) renders (basically) useless. Before Active Record, I had to tirelessly write out every little method like #name, #name=, and so on and so forth. Now, with Active Record, so long as you create the table in the correct fashion, with the correct column names, it is taken care of for you. 




