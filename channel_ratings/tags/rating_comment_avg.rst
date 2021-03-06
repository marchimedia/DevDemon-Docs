##################################
RATING: Average Comment Rating
##################################
::

  {exp:channel_ratings:rating_comment_avg}
      <!-- Template Code -->
  {/exp:channel_ratings:rating_comment_avg}

This tag will display an AVERAGE rating of all comments for a specific entry.

.. contents::
  :local:

***********************
Parameters
***********************

entry_id=""
============
The entry id

url_title=""
============
Same as entry_id="" but now uses the url_title of the entry

.. important:: You MUST use one of the above parameters.

collection=""
==============
Limit by rating collection.

**Default:** collection="default"

precision=""
==============
This parameter allows you to specify the number of decimals to round fractions on numerical rating fields for averages.
For example, a value of 1 would give you a result like this for a rating value: 4.5

**Default:** precision="2"

thousands=""
==============
This parameter allows you to specify which character to use to separate groups of thousands in numeric rating fields. For example, a value of , would parse 10000 as 10,000. Default is , (comma).

**Default:** thousands=","

fractions=""
==============
This parameter allows you to specify which character to indicate fractions in numeric ratings. (Decimals)

**Default:** fractions="."

scale=""
==============
By default, Channel Ratings assumes your rating scale is 5. As in, your numerical ratings are out of 5 (ex: 1 out of 5 stars, 2 out of 5 stars, etc). You can however, change the scale to be out of "10" by specifying the scale parameter. When you specify this, the stars variable pairs will switch from the default of 5 graphic images to 10 when placed around your numerical rating value.

**Default:** scale="5"

theme=""
==============
Since you can have your own custom themes, this parameter allows you to specify which theme to use.

**Default:** theme="stars"

prefix=""
=============
This parameter allows you to change the default variable prefix used. This is especially useful when you are nesting tags to avoid variable collisions.

**Default:** prefix="rating"

For example the variable `{rating:count}`, if you use prefix="cr" the variable will now be {cr:count}

**********************
Variables
**********************

{rating:FIELDNAME:avg}
=========================
This variable outputs the overall average rating value for the specified field

{rating:FIELDNAME:total}
==========================
This variable outputs the total amount of ratings submitted for the specified field

{rating:FIELDNAME:sum}
=======================
This variable outputs the total cumulative value/score of all ratings submitted for the specified field

{rating:FIELDNAME:latest_date}
================================
The date/time of the latest rating submission for the specified field
For date variable info see: http://expressionengine.com/user_guide/templates/date_variable_formatting.html

{rating:FIELDNAME:stars}
=========================
This variable outputs "star" images to construct a graphical representation of the overall average rating value for the specified field

{rating:overall:avg}
======================
This variable outputs the overall average rating value for all fields.

{rating:overall:total}
========================
This variable outputs the total amount of ratings submitted for all fields.

{rating:overall:sum}
=====================
This variable outputs the total cumulative value/score of all ratings submitted for all fields.

{rating:overall:latest_date}
=============================
The date/time of the latest rating submission for all fields.
For date variable info see: http://expressionengine.com/user_guide/templates/date_variable_formatting.html

{rating:overall:stars}
=======================
This variable outputs "star" images to construct a graphical representation of the overall average rating value for all fields.

****************************
Conditionals
****************************

{if rating:no_rating}
======================
This tag will conditionally display the code inside the tag if there are no stats to display

**********************
Example
**********************
::

	{exp:channel_ratings:rating_comment_avg entry_id="{entry_id}"}
	
		Price: {rating:price:stars} ({rating:price:avg} of 5)
		Shipping: {rating:shipping:stars} ({rating:shipping:avg} of 5)
		OVERALL: {rating:overall:stars} ({rating:overall:avg} of 5)
		
	{/exp:channel_ratings:rating_comment_avg}