#ArchivesSpace public views

The views for the public side of ArchivesSpace have been altered to achieve the following:

* Add the identifier column to the display and allow for sorting.
   * The file `views/search/_inline_results.html.erb` checks for the `identifier` field (`digital_object_id` in the case of digital objects), and adds that as a floating span to display to the right of the linked title of the item.
   * The file `views/search/_pagination_summary.html.erb` was altered to add the identifier (or digital_object_id) to the `@search_data.sort_fields` for use in the the sort options.

	Adding the digital object id as a sort option requires that the `locales/en.yml` be overwritten to include the translation for the search_sorting section

	search_sorting:
		digital_object_id: Identifier (or whatever label)

- Disabling the instances just means removing the lines rendering the partial views of the instances from two files:
   
   `views/records/accession.html.erb`
   
   `views/records/resources.html.erb`
