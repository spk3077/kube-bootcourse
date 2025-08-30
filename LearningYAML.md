# Learning YAML
Lists of Objects in YAML is a bit confusing
JSON equivalent:
[
    {
        "name": "Glorfindel",
        "race": "elf"
    },
    {
        "name": "Thorin",
        "race": "dwarf"
    }
]
YAML Equivalent:
- name: Glorfindel
  race: elf
- name: Throin
  race: dwarf

YAML multiline strings:
multiline_string_var: |
    this is a
    multiline string
    string in YAML.
- The single | pipe character makes it a multiline
- You can swap the pipe with a > to make it a single line string (removes  \n)

YAML uses either two or four spaces for identation. Just keep it consistent

