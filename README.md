# UAAG as JSON
This is meant to be like [WCAG as JSON](https://github.com/tenon-io/wcag-as-json) and [andrewnordlund/atag-as-json: ATAG Quick Reference in JSON](https://github.com/andrewnordlund/atag-as-json) but for UAAG.

## Relevant Links
* [uaag-as-json - npm](https://www.npmjs.com/package/uaag-as-json)
* [User Agent Accessibility Guidelines (UAAG) 2.0](https://www.w3.org/TR/UAAG20/)


## Structure

The structure of the JSON file closely mirrors the UAAG Standard itself:

* There are 5 Principles of UAAG (Perceivable, Operable, Understandable, Programmatic access, and Specifications and conventions)
* Each Principle has Guidelines
* Each Guideline has Success Criteria

In this JSON format the Success Criteria have been broken down further:

* Special Cases - additional considerations on the applicability of the SC. There are 3 types of special cases
  * `exception` - the special case, if satisfied, creates an exception whereby the SC does not apply
  * `at_least_one` - at least one of the special cases must apply 
  * `all_true` - all of the special cases must apply 
* Notes - any other notes that accompany the Success Criterion
* The Level of a Success Criterion is either A, AA, AA, or A,AA,AAA meaning the SC corresponds to the desired level of WCAG conformance.

A full UAAG SC Entry looks like this:

```
{
	"ref_id" : "sc_114",
	"title" : "Facilitate Clear Display of Alternative Content for Time-based Media",
	"description" : "For recognized on-screen alternative content for time-based media (e.g. captions, sign language video), the following are all true",
	"level" : "A",
	"url_fragment" : "sc_114",
	"notes" : [
		{ "content" : "Depending on the screen area available, the display of the primary time-based media can need to be reduced in size to meet this requirement. " }
	],
	"special_cases" : [
		{
			"type": "all_true",
			"title": "Don't obscure controls",
			"description": "Displaying time-based media alternatives doesn't obscure recognized controls for the primary time-based media."
		},
		{
			"type": "all_true",
			"title": "Don't obscure primary media",
			"description": "The user can specify that displaying time-based media alternatives doesn't obscure the primary time-based media. "
		}
	]
},
```

## License
The JSON formatted document has an MIT license.

This software or document includes material copied from or derived from User Agent Accessibility Guidelines (UAAG) 2.0 https://www.w3.org/TR/UAAG20/. Copyright © 2015 W3C® (MIT, ERCIM, Keio, Beihang).
