# 1990

Make your Github history back to 1990.

![image](https://user-images.githubusercontent.com/11247099/89427797-38f24f80-d76e-11ea-84fa-ab5642751792.png)

## Travel Back

[Create a new repo](https://github.com/new) named `1990` on Github.

Run the following script

```bash
$ sh -c "$(curl -fsSL https://raw.github.com/antfu/1990-script/master/index.sh)"
```

Enter you Github username and you are done :)

## Explanations

This project works on the way `git` records commit. Whenever you commit something, `git` puts an `Unix Timestamp` on it to record when you committed it. An [`Unix Timestamp`](https://www.unixtimestamp.com/) is the way computers store the current time. An `Unix timestamp` is a `32-bit` number which stores the number of seconds that has passed from January 1st, 1970 at UTC, the `Unix Epoch`.

The script firstly creates a directory with the name of the wanted year - `line 9` `mkdir $YEAR`

The script then initializes the directory as a git repository, using `git init` - `line 12` `git init`

The script then stages all the files `git add .` and commits it, using the date `{YEAR}-01-01T18:00:00` (`line 16`) or `6pm, 1st January, 1990` (default of the `YEAR` variable)

This is the `ISO Date-Time format` for storing time: `YYYY-MM-DDTHH:MM:SS`.

This commit is then pushed to GitHub (provided you already have made a repository) using `git push -u origin main -f`, and the directory is removed.

GitHub recognizes the commit to have been created at `6 pm, 1st January, 1990` and thus registers a contribution at that moment in time. If you scroll to the first year on your profile, you will see there is a single contribution to your `1990` repository, on 1st January.
