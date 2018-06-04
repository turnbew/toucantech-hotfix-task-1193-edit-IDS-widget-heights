FOR PRIVACY AND CODE PROTECTING REASONS THIS IS A SIMPLIFIED VERSION OF CHANGES AND NEW FEATURES

TASK DATE: 21.11.2017 - FINISHED: 22.11.2017 

TASK LEVEL: EASY - symple css manipulation

TASK SHORT DESCRIPTION: 1193 (OK HUB (ids-ok-hub) & Eldis Job feed (ids-job-widget-container) widgets to be made smaller height wise. Use same height as 'search for people' widget.)
	
GITHUB REPOSITORY CODE: hotfix/task-1193-edit-IDS-widget-heights

CHANGES
 
	IN FILES: 
	
		nb_metadata.html
		metadata.html
		metadata.html
		nb_metadata.html
		metadata.html
		
		
			ADDED CODE: 
			
				{{ asset:css file='widget-manipulation.css' group="static" }}
	
		ADDED NEW FILE: 
		
			widget-manupulation.css
			\widget-manupulation.css
			widget-manupulation.css
			
			CODE IN IT: 
					
				div#open-knowledge-hub-widget-content {
					height: 40%;
				}
				div#open-knowledge-hub-widget-content>ul.okhub_list {
					height: 150px;
					min-height: 150px;
				}

				div.widget.ids_jobs_feed {
					margin-bottom: 10px;
				}
				div.widget.ids_jobs_feed > div.ids-job-widget-container > div.ids-jobs-feed-widget {
					height: 350px;
					min-height: 350px;
				}
