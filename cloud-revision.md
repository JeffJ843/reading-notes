External CSS
external style sheet can change the look of an entire website by changing just one file!
Each HTML page must include a reference to the external style sheet file inside the <link> element, inside the head section
Internal CSS
An internal style sheet may be used if one single HTML page has a unique style.
The internal style is defined inside the <style> element, inside the head section.
Inline CSS
An inline style may be used to apply a unique style for a single element.
To use inline styles, add the style attribute to the relevant element. The style attribute can contain any CSS property.
Multiple Style Sheets
If some properties have been defined for the same selector (element) in different style sheets, the value from the last read style sheet will be used. 
Cascading Order
What style will be used when there is more than one style specified for an HTML element?
All the styles in a page will "cascade" into a new "virtual" style sheet by the following rules, where number one has the highest priority:
1. Inline style (inside an HTML element)
2. External and internal style sheets (in the head section)
3. Browser default






