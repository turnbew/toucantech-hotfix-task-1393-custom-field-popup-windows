FOR PRIVACY AND CODE PROTECTING REASONS THIS IS A SIMPLIFIED VERSION OF CHANGES AND NEW FEATURES

TASK DATE : 09.11.2017 - FINISHED: 09.11.2017

TASK'S LEVEL: (EASY)

TASK SHORT DESCRIPTION: 1393 [
								Bug - custom field pop up javascript bug - only able to select one custom field 
								before page is reloaded. Selecting another custom field will open up the first 
								custom field opened. A new field is only opening when page is reloaded.
							]
							
GITHUB REPOSITORY CODE: hotfix/task-1393-custom-field-popup-windows

CHANGES
 
	IN FILES: 
	
		system_fields_industries_modal.js
		custom_questions.jsú
		
			Changes in all modal call function put the next things
			
			For example: 
			
			//display industry types modal
			if ($("#edit-industry-types")) {
				$("#edit-industry-types").on("click", function(event) {		//ADD EVENT parameters
					event.preventDefault();									//ADD prevent event
					$('.modal-content').empty();							//Clear modal content - avoiding caching
					$('#industry-types-modal')
						.removeData('bs.modal')								//Clear bootstrap modal content - avoiding caching
						.modal({
							remote: '...........ajax_industry_types_dialog'
						});
					$('.popover-dismiss').popover({trigger: 'hover'});
				})	
			}
