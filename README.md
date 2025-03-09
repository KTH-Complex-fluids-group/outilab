# Complex Fluids group

This is the website of our academic research group at KTH, Sweden.\
The website is live at: [https://kth-complex-fluids-group.github.io/outilab/](https://kth-complex-fluids-group.github.io/outilab/)

This website is powered by Jekyll and some Bootstrap, Bootwatch.

## Outilab Website Management Guide

This guide provides step-by-step instructions for editing and managing the Outilab website hosted on GitHub Pages.

---

## Step 1: Clone the Repository

To get started, clone the repository and navigate into the project directory:

```
git clone -b gh-pages git@github.com:KTH-Complex-fluids-group/outilab.git
cd outilab
```

---

## Step 2: Editing Content

### 2.1 Editing the Home Page

To edit the home page:

```
cd _pages
open home.md
```

- Make your edits to `home.md`.
- Save your changes.
- Proceed to **Step 3** to commit and push your changes.

---

### 2.2 Editing Team Information

To update team information (e.g., members, alumni, etc.):

    cd _data


The following files contain specific team-related data:

| File Name              | Description                                      |
|------------------------|--------------------------------------------------|
| `pi.yml`               | Data about the project responsible/PI.          |
| `phd.yml`              | Details of PhD students.                        |
| `alumni_msc.yml`       | Alumni Master students.                         |
| `alumni_visitors.yml`  | Visiting PhD students.                          |
| `alumni_bsc.yml`       | Alumni Bachelor students.                       |
| `alumni_members.yml`   | Alumni lab members.                             |
| `students.yml`         | Current Bachelor and Master students.           |
| `postdoc.yml`          | Post-docs in the group.                         |

To edit any of these files:

1. Open the corresponding file:
    open <filename>.yml
2. Make your edits.
3. Save your changes.
4. Note: Team member images should be placed in the `outilab/images/teampic/` directory.

Proceed to **Step 3** to commit and push your changes.

---

### 2.3 Adding Publications

To add or update publications:

```
cd _data
open publist.yml
```

Add a new publication entry in the following format:

```
title: <Title of paper>
authors: List separated by "and"
url: <URL of the paper>
display: <Display name for the link>
highlight: <Position of group author starting from 1; use 0 if none>
pihighlight: <Negative position of PI (e.g., -1 if last author)>
```

Save your changes and proceed to **Step 3**.

---

### 2.4 Updating Defence Dates or Calendar Events

To update student defence dates or group calendar events:

```
cd _pages
open calendar.md
```

- Make your edits.
- Save your changes.
- Proceed to **Step 3**.

---

### 2.5 Updating News

To add or update news items:

```
cd _data
open news.yml
```

Add a new news entry in the following format:

```
date: <YYYY-MM-DD>
headline: <Short description of the news>
```

You can include links in the news description using HTML tags like this:

    <a href="{link}">some text</a>

Save your changes and proceed to **Step 3**.

---

### 2.6 Updating Group Pictures

To update group pictures:

1. Add new images to the `outilab/images/picpic/` directory.
2. Reference these images in `pictures.md`:
```
cd _pages
open pictures.md
```

- Add headings, figure names, and references as needed.
- Save your changes.
- Proceed to **Step 3**.

---

### 2.7 Updating Slider Images on the Home Page

To change slider images on the home page:

1. Navigate to the slider images directory:
    cd images/slider
2. Replace any image with a new one (preferably `.png` format).
3. Rename it using the format:

    home{num}.png (e.g., home1.png, home2.png)
4. Save your changes.
5. Proceed to **Step 3**.

---

## Step 3: Commit and Push Changes

After making any edits, follow these steps to commit and push your changes to GitHub:


```
git add *
git commit -m '{Your descriptive commit message}'
git push origin gh-pages
```

---

## Notes

- Ensure that all image files are correctly placed in their respective directories (`teampic`, `picpic`, or `slider`) before committing.
- Use descriptive commit messages to track changes effectively.

---

This README provides a comprehensive guide for managing all aspects of the Outilab website efficiently.


Go to *aboutwebsite.md*  to learn how to copy and modify this page for your purpose. 

Copyright OutiLab. Code released under the MIT License.

