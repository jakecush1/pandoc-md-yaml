standard pandoc goes md -> html

commands:
pandoc file.md -s
-> outputs the md file as html
you can use -s (standalone) and it will wrap the file in an html template

pandoc file.md -o newfile.html
-> converts md to html and saves as a new file

using -f (from) and -t (to) to choose directions, -o (output) save as new file
pandoc newfile.html -f html -t markdown -o newmd.md
-> converts newfile.html from html to markdown and saves output as newmd.md

Pandoc can convert to many other file types as well, check outputs 
--list-output-formats

Stacking files markdown together can be down like this
pandoc demographic.md population.md -t markdown  

pandoc has premade templates it uses when converting, you can use a custom template by specifying --template

**templates contain variables, which allow for inclusion of information at any point in the file.  Variables can be set using yaml metadeta blocks, but the variables must be defined in the template in order to access them.

to mark variables and control structure in the template, use $vName$ delimiters or ${vname}

native output causes metadata to be included,
-s, --standalone produces output with appropriate header and footer (html, latex etc)

--metadata-file=FILENAME -> Read metadata from the supplied YAML

Variables
[pandoc-mustache](https://github.com/michaelstepner/pandoc-mustache), and lau extension are also options for variable inclusion

-> if metadata / frontmatter yaml is inside the markdown file, this command works for subbing in variables
pandoc population.md --template population.md

-> meta data in variables.yaml file, subs in variables
pandoc demographic.md --template demographic.md --metadata-file=variables.yaml

-> using the md file as the template works, so far is my best way of subbing variables, you can stack multiple by using &&
pandoc demographic.md --template demographic.md --metadata-file=variables.yaml --metadata title="demographic" && ...

testing with actual indicators, first using hardcoded variables inside of the indicators, to test pulling data from yaml file. later these variables would be set based on user selection

dec 8/ 22

Figure out new structure removing the location name as the objects parent.  dont need that and ti fixes the problem of having to specify location in markdown file.

