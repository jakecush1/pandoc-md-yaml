# Community Profiles Pandoc demo

-> meta data in location.yaml file
-> indicator is markdown file

See demograpics_population.md file. The variables which receive data from the yaml file has a hardcoded location name in it.  Maybe my structure of the yaml file is wrong?

navigate to a directory with files demographics_population.md and nelson.yaml inside

run command:
```
pandoc demographics_population.md --template demographics_population.md --metadata-file=nelson.yaml
```

