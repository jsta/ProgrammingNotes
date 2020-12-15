## GNU Make

### Basics

- `$ make foo`

Force rebuild:

- `$make -B foo`

- `$@` - the target
- `$<` - first prerequisite
- `$^` - all prerequisites
- `$(<F)` - file part of first prerequisite
- `$(<D)` - directory part of first prerequisite
- `$(@D)` - directory part of target
- `$(@F)` - file-within-directory part of target
- `%` - wildcard

- `include` - to include another Makefile (perhaps first defining some variables)

### Advanced

 * Pass a list of targets as a variable

 * File name operations

---

`.PHONY` for indicating not-real targets; see <http://stackoverflow.com/a/7081747/897303>

example:

```
.PHONY: all doc clean
```

---

### Examples

- [gSSURGO](https://github.com/jsta/gSSURGO/Makefile)
