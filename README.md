# javascript_search_bookmarklet

[Use the bookmarklet here.](javascript:
(
	function()
	{
		var counter = 1;
		var terms = [];
		var isDone = false;

		for (;;)
		{
			var term_current = prompt("Enter search term #" + counter + ":","");
			if ((term_current != "") && (term_current != null))
			{
				terms.push(term_current);
				counter++;
			}
			else
			{
				break;
			}
		}
		if (terms != null)
		{
			var terms_all = "";
			for (var i = 0; i < terms.length; i++)
			{
				terms_all = terms_all.concat(terms[i]);
						
				if (i != terms.length - 1)
				{
					terms_all = terms_all.concat(", ");
				}
			}
			location="https://www.google.co.uk/search?q="+escape(terms_all);
		}
	}
)())
