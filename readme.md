### BOT-DATA-COLLECTOR

 - [use database](#use-database)
 - [extending](#extending )

 #### use database
there are 2 collection loaded.
by default use collection from rum_data1.

1. bot setting collection loaded into list in_sett['job_coll']
2. jobs collection loaded into list in_sett['job_coll']

import initialize.py in_sett['job_coll'] as your need to manipulate collection thats rendered on website.

example add new setting:

	
	import in_sett
	in_sett.update_setting(key="1",data='some data')

add new job:


	import in_sett
	in_sett.update_job(id="1",data='some data')



 #### extending: 
 
 ---> listen to changes in message jobs when user edit it:

 extends MessageJob class and override on_message_edit function.
 and import your derived class to auto_message,py

    from message_job import YourClass as MessageJob
    

 
 ---> add additional reply when user posted a job:

 it's turned off by default. a command to turn it on is `!show_info 1`.
  extends BotReply class and override on_message_edit function 
  to add aditional function when user edit message(MessageJob).
  and on_reaction_add when reviewer give reaction to review posted by bot(MessageReview).
 and import your derived class to auto_message,py

    from message_job import YourClass as BotReply

 
 
---> add additional review:

 extends MessageReview class and 
 same as BotReply just overidde any function thats fits your needed.
 and import your derived class to auto_message,py

    from message_job import YourClass as MessageReview

-- listen to other discord.py events

first version this bot only  listen to 5 events.
add more as u need.

-- add another command

there already command1 file for list available command for the bot. 
create new file eg. command2 for additional command and import it to main.py.

 
 



