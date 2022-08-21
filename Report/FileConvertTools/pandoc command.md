<!-- markdown to doc; adding references; during drafting phase -->

pandoc --cite --bibliography=FileConvertTools/Dissertation.bib --csl=FileConvertTools/ucl-institute-of-education-harvard.csl Results.md -o result.docx

<!-- tex to markdown; for further viewing -->
find ./ -iname "*.tex" -type f -exec sh -c 'pandoc "${0}" -o "${0%.docx}.md"' {} \;
