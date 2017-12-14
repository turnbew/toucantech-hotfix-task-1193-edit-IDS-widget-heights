TASK's DATE: 21.11.2017 - FINISHED: 22.11.2017 

TASK's LEVEL: EASY - symple css manipulation

TASK SHORT DESCRIPTION: 1193 (OK HUB (ids-ok-hub) & Eldis Job feed (ids-job-widget-container) widgets to be made smaller height wise. Use same height as 'search for people' widget.)

GITHUB REPOSITORY CODE: hotfix/task-1193-edit-IDS-widget-heights

ORIGINAL WORK: https://github.com/BusinessBecause/network-site/tree/hotfix/task-1193-edit-IDS-widget-heights


CHANGES
 
	IN FILES: 
	
		\network-site\addons\default\themes\toucantechV2\views\partials\nb_metadata.html
		\network-site\addons\default\themes\toucantechV2\views\partials\metadata.html
		\network-site\addons\default\themes\networkbecause\views\partials\metadata.html
		\network-site\addons\default\themes\businessbecause\views\partials\nb_metadata.html
		\network-site\addons\default\themes\businessbecause\views\partials\metadata.html
		
		
			ADDED CODE: 
			
				{{ asset:css file='widget-manipulation.css' group="static" }}
	
		ADDED NEW FILE: 
		
			\network-site\addons\default\themes\toucantechV2\css\widget-manupulation.css
			\network-site\addons\default\themes\networkbecause\css\widget-manupulation.css
			\network-site\addons\default\themes\businessbecause\css\widget-manupulation.css
			
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
