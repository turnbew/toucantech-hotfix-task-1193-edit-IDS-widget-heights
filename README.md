TASK's DATE: 21.11.2017 - FINISHED: 22.11.2017 (MEDIUM - I had to operate on a third party generated code which not sure will be loaded)

TASK SHORT DESCRIPTION: 1193 (OK HUB (ids-ok-hub) & Eldis Job feed (ids-job-widget-container) widgets to be made smaller height wise. Use same height as 'search for people' widget.)

GITHUB REPOSITORY CODE: hotfix/task-1193-edit-IDS-widget-heights

ORIGINAL WORK: https://github.com/BusinessBecause/network-site/tree/hotfix/task-1193-edit-IDS-widget-heights


CHANGES
 
	IN FILES: 
	
		\network-site\addons\default\themes\toucantechV2\views\partials\nb_metadata.html
		\network-site\addons\default\themes\networkbecause\views\partials\metadata.html
		\network-site\addons\default\themes\businessbecause\views\partials\nb_metadata.html
		\network-site\addons\default\themes\businessbecause\views\partials\metadata.html
		\network-site\addons\default\themes\toucantechV2\views\partials\metadata.html
		
			ADDED CODE: 
			
				{{ asset:js file='widget-manipulation.js' group="static" }}
	
		ADDED NEW FILE: 
		
			\network-site\addons\default\themes\toucantechV2\js\widget-manupulation.js
			\network-site\addons\default\themes\networkbecause\js\widget-manupulation.js
			\network-site\addons\default\themes\businessbecause\js\widget-manupulation.js
			
			CODE IN IT: 
					
				var ok_hub_timeinterval; 	
				var ok_hub_timelimit = 3000;	
				var ok_hub_timecounter = 0;	
				var ok_hub_looptime = 100;
				
				var jobs_feed_timeinterval; 	
				var jobs_feed_timelimit = 3000;	
				var jobs_feed_timecounter = 0;	
				var jobs_feed_looptime = 100;

				
				
				function cssSettings_widgetOkHub() 
				{
					ok_hub_timecounter += ok_hub_looptime;
					
					if ($('#open-knowledge-hub-widget-content').find('.okhub_list').length > 0) 
					{
						$('#open-knowledge-hub-widget-content').css('height', '40%');
						$('#open-knowledge-hub-widget-content').find('.okhub_list').css({'height' : '150px', 'min-height' : '150px'});			
						
						clearInterval(ok_hub_timeinterval);
					}
					else if (ok_hub_timecounter > ok_hub_timelimit) //probably the element wasn't loaded into the DOM, doesn't exist
					{
						clearInterval(ok_hub_timeinterval);
					}
				}		

				
				
				function cssSettings_widgetJobsFeed() 
				{
					jobs_feed_timecounter += jobs_feed_looptime;

					if ($('#open-knowledge-hub-widget-content').find('.jobsfeed_list').length > 0) 
					{
						$('#open-knowledge-hub-widget-content').css('height', '40%');
						$('#open-knowledge-hub-widget-content').find('.jobsfeed_list').css({'height' : '150px', 'min-height' : '150px'});			
						
						clearInterval(jobs_feed_timeinterval);
					}
					else if (jobs_feed_timecounter > jobs_feed_timelimit) //probably the element wasn't loaded into the DOM, doesn't exist
					{
						clearInterval(jobs_feed_timeinterval);
					}
				}	
				
				
				//when DOM is loaded
				$(function(){
					ok_hub_timeinterval = setInterval(cssSettings_widgetOkHub, ok_hub_looptime);
					jobs_feed_timeinterval = setInterval(cssSettings_widgetJobsFeed, jobs_feed_looptime);
				})
