## RRCP - rsync copier with checksum verification

```bash
Usage: rrcp [-cxqutdP] SRC [SRC]... DEST

Options:
  -c        clone (mirror)
  -x        use delta-xfer algorithm
  -q        quiet (less output)
  -u        mention unchanged names (more output)
  -t        without test (without post-check)
  -d        do (disable DRY RUN)
  -P        print rsync command, do nothing
```

## Examples

Copy (dry-run - nothing will be copied) the contents of the `src` directory to the `dest` directory:
```bash
rrcp ~/src/ ~/dest/
```
Copy (dry-run - nothing will be copied) the `src` directory to the `dest` directory:
```bash
rrcp ~/src ~/dest/
```
Copy the `src` directory to the `dest` directory:
```bash
rrcp -d ~/src ~/dest/
```
Copy the `name with spaces` directory to the `dest` directory:
```bash
rrcp -d "~/name with spaces" ~/dest/
```
Copy the directories `src1`, `src2`, `src3` to the directory `dest`:
```bash
rrcp -d ~/src1 ~/src2 ~/src3 ~/dest/
```
Copy (do nothing, just print the full `rsync` command) the `src` directory to the `dest` directory:
```bash
rrcp -dP ~/src ~/dest/
```
Clone (delete extraneous files from dest dirs) the `src` directory to the `dest` directory:
```bash
rrcp -cd ~/src ~/dest/
```
