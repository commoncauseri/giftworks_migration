# Notes on Giftworks DB Structure

The dirty little secret about the Giftworks database is that it's a glorified Microsoft Access database. The database repository file natively has a file extension of .gbf (Giftworks Base File? Giftworks Bad Format? Who knows.), but if you change the file extension to .mdb it'll open in Microsoft Access. 

But who the hell has Microsoft Access? Who wants to have it? At the time, we hadn't done a ton of research on open source methods to convert Access databases, so we sucked it up and paid actual money for [MDB Explorer](http://www.macexplorer.co/en/mdb-explorer.php). In the end, it was probably worth it. It did the trick. What we wanted was to be able to take the Access DB and convert it into separate .csv or Excel files. MDB Explorer is just perfect for this. 

One thing to know: to the best of our knowledge, there is no real GiftWorks community online. It's not like you can go and have a discussion with people. We're hopeful that this repo might end up being exactly that spot. We mention this because when we exported from MDB Explorer, you'll end up with a certain set of files. That might be different from ours. We're sure, also, that the exact file list will probably vary by what version of Giftworks you're using. For the record, the writer of this document has no idea what version we were on. We'll update this doc when we figure it out. 

So, our file list looks like this: 

- INTERNAL_locks.csv
- INTERNAL_rights.csv
- INTERNAL_rolemap.csv
- INTERNAL_roles.csv
- INTERNAL_settings.csv
- INTERNAL_usermap.csv
- INTERNAL_users.csv
- INTERNAL_users_data.csv
- actions_actions.csv
- actions_assignments.csv
- donor_campaigns.csv
- donor_contactInfo_addresses.csv
- donor_contactInfo_emails.csv
- donor_contactInfo_phones.csv
- donor_donor_relationships.csv
- donor_donorgroups.csv
- donor_donors.csv
- donor_ext_aggregates.csv
- donor_field_categories.csv
- donor_field_gifts_categories.csv
- donor_field_gifts_metadata.csv
- donor_field_metadata.csv
- donor_funds.csv
- donor_funds_accounts.csv
- donor_gifts.csv
- donor_gifts_payments.csv
- donor_gifts_payments_credits.csv
- donor_gifts_payments_transactions.csv
- donor_list_accounts.csv
- donor_list_activity.csv
- donor_list_addressnames.csv
- donor_list_assignedto.csv
- donor_list_batchentry_definitions.csv
- donor_list_classes.csv
- donor_list_contacttypes.csv
- donor_list_countries.csv
- donor_list_creditcards.csv
- donor_list_custom100.csv
- donor_list_custom101.csv
- donor_list_custom102.csv
- donor_list_custom103.csv
- donor_list_defaultvalues.csv
- donor_list_directedto.csv
- donor_list_donortypes.csv
- donor_list_emailnames.csv
- donor_list_followups.csv
- donor_list_gifts_custom1.csv
- donor_list_gifts_custom2.csv
- donor_list_gifts_custom4.csv
- donor_list_gifts_payment_subtype.csv
- donor_list_gifts_payment_type.csv
- donor_list_gifts_solicitors.csv
- donor_list_gifts_sources.csv
- donor_list_group.csv
- donor_list_honorariums.csv
- donor_list_honorariums_notify.csv
- donor_list_howacknowledged.csv
- donor_list_mailing_definitions.csv
- donor_list_mailinglists.csv
- donor_list_notetitles.csv
- donor_list_phonenames.csv
- donor_list_prefixes.csv
- donor_list_receiptgroups.csv
- donor_list_roles.csv
- donor_list_source.csv
- donor_list_states.csv
- donor_list_status.csv
- donor_list_suffixes.csv
- donor_list_titles.csv
- donor_lists.csv
- donor_mailing_lists.csv
- donor_mailing_templates.csv
- donor_reports.csv
- donor_saved_lists.csv
- donor_saved_lists_categories.csv
- donor_saved_lists_filters.csv
- donor_saved_reports.csv
- donor_saved_smartentry.csv
- donor_transaction_batch.csv
- events_event_activities.csv
- events_event_expenses.csv
- events_event_info.csv
- events_event_participants.csv
- events_event_participants_groups.csv
- events_event_reservations.csv
- events_event_reservations_activities.csv
- events_event_tasks.csv
- events_list_eventcategories.csv
- events_list_eventcoordinators.csv
- events_list_eventinvitationgroups.csv
- events_list_eventlocations.csv
- events_list_eventstatuses.csv
- history.csv
- history_entities.csv
- volunteer_job_assignments.csv
- volunteer_job_schedules.csv
- volunteer_job_skills.csv
- volunteer_jobs.csv
- volunteer_list_jobmanagers.csv
- volunteer_list_projects.csv
- volunteer_list_skills.csv
- volunteer_list_skillscategories.csv
- volunteer_list_volunteermanagers.csv
- volunteer_volunteer_availability.csv
- volunteer_volunteer_hours.csv
- volunteer_volunteer_skills.csv
- volunteer_volunteer_info.csv

In this project, we'll basically be detailing how each of these tables interacts with each other, how to unify the data, and how to get it into the Non-Profit Starter Pack (NPSP) Data Import Format.

Our data was filthy (one of the reasons we've gotten crazy about data validation in our new Salesforce for Non-Profits instance), so post-extraction, we had two tasks: Clean up this old, filthy data, and figure out how it all talks to each other. For cleanup, we used every trick in the book for [Google Sheets](https://support.google.com/docs?hl=en&authuser=1#topic=1382883). Particularly helpful was the =unique command, for narrowing down where data had to be standardized.

Only late in the game did we discover [OpenRefine](http://openrefine.org/). We sincerely wish we'd discovered it sooner. It's an extremely powerful tool for cleaning messy data. 

More to come soon... 