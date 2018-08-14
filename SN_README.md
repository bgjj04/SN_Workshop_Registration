# Developer Information
Jonathan R. Jackson  
jacksonjonathan@gmail.com  
http://www.jonathanrjackson.com/  

# Overview
Workshop/training registration scoped application.

This application is used to track attendees to training/workshops/events that your organization provides.
Users can self-service register and unregister for workshops.
Workshop managers can add new events, assign instructors, date/time, & maximum attendees.

# Tables
* x_34314_wrkshp_reg_workshops :: Workshops
    * Contains the workshop records
    * Fields:
     *   Workshop Name (workshop_name), string (Full UTF-8, 255), The name of the workshop
     *   Description (description), string(Full UTF-8, 5,000), Long description of the workshop
     *   Max Attendees (max_attendees), integer (10), Maximum number of attendees that can be registered for the workshop
     *   Location (location), string (Full UTF-8, 255), The location/room of the workshop
     *   Start Time (start_time), date/time, The date/time that the workshop is scheduled to begin
     *   End Time (end_time), date/time, The date/time that the workshop is scheduled to end
     *   Instructor(s) (instructors), reference to sys_user, A list collector of the instructors assigned to instruct the workshop
* x_34314_wrkshp_reg_workshop_attendees :: Workshop Attendees
     * Many-to-many table linking attendees (via sys_user) to a workshop (via x_34314_wrkshp_reg_workshops)
     * Fields:
        * Attendee (attendee), reference to sys_user, The attendee of a workshop
        * Workshop (workshop), reference to x_34314_wrkshp_reg_workshops, The workshop that the attendee is attending
        * Attended Workshop (attended_workshop), True/False, Indicator of whether the attendee attended the workshop.

