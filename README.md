# RESTYLEgc
Fork of restylegc - a php hook  to allow custom styling of a google calendar without the need to call on calviz.

##DESCRIPTION:
 This script is an intermediary between an iframe and Google Calendar that
 allows you to override the default style.

##USAGE:
```
<iframe src="restylegc.php?src=user%40domain.tld"></iframe>
```
 
 Example with some optional parameters
 ```
 <iframe src="http://www.yourdomain.com/restylegc.php?
 title=Your title&showNav=0&
 showDate=0&showPrint=0&showTabs=0&showCalendars=0&
 showTz=0&mode=AGENDA&height=600&wkst=2&hl=nl&
 bgcolor=%23FFFFFF&src=user%40domain.tld&
 color=%23125A12&src=3ssm39l64snn6kolqndta8p2o4%40group.calendar.google.com&
 color=%23711616&ctz=Europe%2FAmsterdam&
 customcss=http://www.yourdomain.com/css/custom.css"
 style="border-width:0" width="230" height="300" frameborder="0" scrolling="no"></iframe>
 ```
 where user@domain.tld is a valid Google Calendar account.
 
##VALID QUERY STRING PARAMETERS:
|     param         |                         value
|:-----------------:|:----------------------------------------------------------:|
|   title        | any valid url encoded string |
|                |    if not present, takes title from first src                  |
|   showTitle    | 0 or 1 (default)                                                 |
|   showNav      | 0 or 1 (default)                                          |
|   showDate     | 0 or 1 (default)                                               |
|   showTabs     | 0 or 1 (default)                                                |
|   showCalendars| 0 or 1 (default)                                                  |
|   mode         | WEEK, MONTH (default), AGENDA                                            |
|   height       | a positive integer (should be same height as iframe)                     |
|   wkst         | 1 (Sun; default), 2 (Mon), or 7 (Sat)                                    |
|   hl           | en, zh_TW, zh_CN, da, nl, en_GB, fi, fr, de, it, ja, ko,                        |
|                |   no, pl, pt_BR, ru, es, sv, tr                                          |
|                |   if not present, takes language from first src                             |
|   bgcolor      | url encoded hex color value, #FFFFFF (default)                                |
|   src          | url encoded Google Calendar account (required)                        |
|   color        | url encoded hex color value      \                                         |
|                | must immediately follow src                                   |
|   customcss    |provide absolute url to the location of your css file.\                |
|                |  an etra link tag will be added to the source to laod your css file. |
                                                                                     
   The query string can contain multiple src/color pairs.  It's recommended
   to have these pairs of query string parameters at the end of the query
   string.


##HISTORY:

|    date           |              description                            |
|:-----------------:|:---------------------------------------------------:
|  03 December 2008 | Original release
|                   |  Uses technique from MyGoogleCal2 for all browsers,
|                   |  rather than giving IE special treatment.
|  16 December 2008 | Modified restylegc-js.php so that the regex does a
|                   |  general match rather than specifically look for the
|                   |  variable 'Ac'.
|  Mar--Apr    2009 | Added jQuery for modifying the style after page load
|  23 June     2009 | Replaced jQuery with Dojo since jQuery, Prototype, and
|                   |  MooTools are not compatible
|  03 July     2009 | Fixed bug to remove width style from bubble
|  05 July     2009 | Rebranded to RESTYLEgc
|  16 August   2009 | Updated regex in restylegc-js.php
|  19 December 2009 | Removed MyGoogleCal references
|                   |  Updated Dojo version
|                   | Archived additional .js and .css files
|  13 November 2010 | Changed Google Calendar protocol to https
|                   |  Switched back to jQuery
|  03 June     2011 | Put jQuery in no-conflict mode
|  18 June     2011 | Fixed bug to remove width style from bubble
|  23 February 2017 | Fixes for google calendar updated references.
|                   |  Removed restyle.css. Use customcss paramter to provide url to your
|                   |  css file that overrides google calendar css
 
##ACKNOWLEDGMENTS:
  Michael McCall (http://www.castlemccall.com/) for pointing out "htmlembed"</br>
  Mike (http://mikahn.com/) for the link to the online CSS formatter</br>
  TechTriad.com (http://techtriad.com/) for requesting and funding the
      Javascript code to edit CSS properties and for selflessly letting the
      code be published for everyone's use and benefit.</br>
  Steve Sawaya (http://sawayaconsulting.com/) for the jQuery no-conflict patch </br>
  Elroy Peters for fixing the code after google calendar upgrade to https</br>
 
