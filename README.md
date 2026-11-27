<p align="center">
<img src="https://i.imgur.com/fC0aNrA.png" height="40%" width="60%" alt="Linux"/>
</p>
<h1>Linux Exercise: Deleting, Moving, & Copying</h1>

In this exercise, I practiced deleting, moving, renaming, and copying files and directories from the Linux command line while building on my previous knowledge of relative paths, file creation, and directory management.

Credit to Colt Steele’s Udemy course, **The Linux Command Line Bootcamp: Beginner to Power User**, for providing both the exercise and the knowledge needed to complete it.
<br />

<h2>Commands, Options, & Shell Features</h2>

- `rm` — Removes files and, with the appropriate options, directories.
  - `-r` — Recursively removes directories and their contents.
  - `-I` — Prompts for confirmation once before removing more than three files or performing a recursive removal.
- `mv` — Moves or renames files and directories.
- `cp` — Copies files and, with the appropriate options, directories.
  - `-r` — Recursively copies directories and their contents.
- `mkdir` — Creates directories.
  - `-p` — Creates any necessary parent directories that do not already exist.
- `touch` — Creates empty files if they do not already exist or updates the timestamps of existing files.
- `ls` — Lists directory contents.
  - `-R` — Recursively lists directories and their contents.
- Honorable mentions (Bash shell features):
  - `&&` — Executes the next command only if the preceding command completes successfully.
  - `{}` — Brace expansion, which generates multiple strings from a single expression.

<h2>The Exercise</h2>

Before we can delete, move, or copy things...we need things! It's time to get some more practice using `touch` and `mkdir`

1. Please create a new directory somewhere on your machine called `Bootcamp`. Inside it, create the folders and files indicated below:

- **Bootcamp/**
	- **FallCohort/**
		- Italo.txt
		- Edgar.txt
		- Linus.txt
		- Sara.txt 
		- Silvio.txt
		- **Waitlist/**
			- Hanna.txt
			- Haris.txt
			- Netta.txt
	- **WinterCohort/**
		- Santiago.txt
		- Iris.txt
		- Naomi.txt

2. Sadly, `Edgar` had to drop out of the course. Delete the `Edgar.txt` file in `FallCohort`.
3. This means we now have space in our Fall Cohort to move someone off of the waitlist. Please move `Netta.txt` from the `Waitlist` folder into the `FallCohort` folder.
4. Please delete the `Waitlist` folder and its contents.
5. It turns out that I misspelled Sara. She spells her name "Sarah" with an "h" at the end. Please rename the `Sara.txt` file to `Sarah.txt`.
6. Unfortunately, Italo is having a bit of a personal emergency, and he would like to move to our Winter Cohort. Please move the `Italo.txt` file from `FallCohort` to the `WinterCohort` folder.
7. Our entire Winter Cohort had to be cancelled because of a worldwide pandemic. We decided to bump all of the scheduled winter students to spring. In the `Bootcamp` directory, create a copy of the `WinterCohort` folder called `SpringCohort`.
8. Please rename the `WinterCohort` folder to `WinterCohortCANCELLED`.
9. We're going out of business. Please delete the entire `Bootcamp` directory.

<h2>What I Did</h2>

**1. Please create a new directory somewhere on your machine called `Bootcamp`. Inside it, create the folders and files indicated above in "The Exercise".**
<p>
<img src="https://i.imgur.com/uL2Qyat.png" height="100%" width="100%"/>
</p>

I used `mkdir -p` with brace expansion to create the required directory structure, followed by `touch` with brace expansion to create all the necessary files. I connected the two commands using `&&` to ensure that the files would only be created if the directory creation was successful. I then used `ls -R` to recursively list the contents of `Bootcamp` and confirm that the structure matched the exercise requirements.

(Edit to add: After completing this step, I learned that I could make the command even more concise by using nested brace expansion and specifying the .txt extension only once, as shown below.)
<br />
`touch Bootcamp/{FallCohort/{Italo,Edgar,Linus,Sara,Silvio},FallCohort/Waitlist/{Hanna,Haris,Netta},WinterCohort/{Santiago,Iris,Naomi}}.txt`

<br />
<br />

**2. Sadly, `Edgar` had to drop out of the course. Delete the `Edgar.txt` file in `FallCohort`.**
<p>
<img src="https://i.imgur.com/qM5Ig7e.png" height="100%" width="100%"/>
</p>

I used `rm` with a relative path to delete `Edgar.txt` from the `FallCohort` directory without leaving my current working directory. I then used `ls` to confirm that the file was no longer present.

<br />
<br />

**3. This means we now have space in our Fall Cohort to move someone off of the waitlist. Please move `Netta.txt` from the `Waitlist` folder into the `FallCohort` folder.**
<p>
<img src="https://i.imgur.com/L6Ausjx.png" height="100%" width="100%"/>
</p>

I used `mv` with relative paths to move `Netta.txt` from the `Waitlist` subdirectory into its parent directory, `FallCohort`. I then used `ls` to check the contents of both directories and confirm that the file had been moved successfully.

<br />
<br />

**4. Please delete the `Waitlist` folder and its contents.**
<p>
<img src="https://i.imgur.com/01gGih4.png" height="100%" width="100%"/>
</p>

I used `rm -rI` to recursively delete the Waitlist directory and its contents while being prompted for confirmation before proceeding. After confirming the removal, I used `ls -R` to verify that the `Waitlist` directory and its remaining files were no longer present in the Bootcamp directory structure.

<br />
<br />

**5. It turns out that I misspelled Sara. She spells her name "Sarah" with an "h" at the end. Please rename the `Sara.txt` file to `Sarah.txt`.**
<p>
<img src="https://i.imgur.com/N4921JT.png" height="100%" width="100%"/>
</p>

I used `mv` to rename `Sara.txt` to `Sarah.txt` by specifying the original and new filenames using relative paths within the same directory. I then used `ls` to confirm that the file had been renamed successfully.

<br />
<br />

**6. Unfortunately, Italo is having a bit of a personal emergency, and he would like to move to our Winter Cohort. Please move the `Italo.txt` file from `FallCohort` to the `WinterCohort` folder.**
<p>
<img src="https://i.imgur.com/PcSVWkD.png" height="100%" width="100%"/>
</p>

Lorem ipsum

<br />
<br />

**7. Our entire Winter Cohort had to be cancelled because of a worldwide pandemic. We decided to bump all of the scheduled winter students to spring. In the `Bootcamp` directory, create a copy of the `WinterCohort` folder called `SpringCohort`.**
<p>
<img src="https://i.imgur.com/5z0Ywra.png" height="100%" width="100%"/>
</p>

Lorem ipsum

<br />
<br />

**8. Please rename the `WinterCohort` folder to `WinterCohortCANCELLED`.**
<p>
<img src="https://i.imgur.com/sWgIltv.png" height="100%" width="100%"/>
</p>

Lorem ipsum

<br />
<br />

**9. We're going out of business. Please delete the entire `Bootcamp` directory.**
<p>
<img src="https://i.imgur.com/4zhuiry.png" height="100%" width="100%"/>
</p>

Lorem ipsum

<br />
<br />

<p>
✨ Lorem ipsum
</p>
<br />
