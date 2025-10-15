# Emile
Utility for painless blogging with Zola.

---

<b>Emile</b> is a little script I wrote in shell script (bash) to make my life easier while blogging with Zola. <br>
I thought more people could benefit from it, so I polished it up and put it on Github. <br>  Feel free to use it, modify, redistribute under GNU General Public License terms. <br>
I hope it makes your bloggnig life easier (and that you apprecate the pun).

---

## Config file
Emile uses a config file in your home directory called <i>.emilerc</i>. <br>
This config file follows the TOML standard and at the moment contains the following info:
- all the blogs you registered for use with Emile
- your favourite editor (otherwise it falls back in the one defined in your environment in $EDITOR)
- your timezone of choice (otherwise it fallsback on the one defined in your environment in $TZ) 

## Register a blog
You can register a blog under a label for easy access through the following command: <br> 
`emile set blogs <label> <posts_dir>`

You want the posts_dir to be the directory where your posts live, in your Zola blog.

E.g. <br> 
`emile set nightcup ~/code/blog/cotent/posts`

## Write a blog post
You can write a new blog post in two ways:

- by referring to a registered blog: <br> 
`emile new <label> "Post title" [-t tag1,tag2] [-c Category] [-e none|/editor]`
- by specifying the path where the blog post should be created: <br> 
`emile new -d <posts_dir> "Post title" [-t tag1,tag2] [-c Category] [-e none|/editor]`

E.g. <br> 
`emile new nightcup "New Post" -t blogging,casual -c "Casual Posts"` <br> 
`emile new -d ~/code/blog/content/posts/ "New Post" -t blogging,casual -c "Casual Posts"`

The new blogpost will be created following those steps:
- A new folder will be created with the slugified title of the post as name.
e.g. if the post name was "New Post", the folder will be named "new-post"
- Inside the newly created post, emile will create an index.md containing a minimal header containig title, date, draft and taxonomies (tags and categories)
- if you didn´t use `-e none`, emile will try to open the post with your favourite text editor (either defined in .emilerc, in $EDITOR or if you passed it as a parameter via `-e`)

## Set your favourite editor
Emile allows the creation of some config variables. <br> 
You can set your favourite editor using the command `set` as follows: <br> 
`emile set config editor /path/to/editor` <br> 

The chosen editor will be saved in the config file .emilerc residing in your home. <br> 
When you set your favourite editor, emile will use it to open your posts when you create one. <br> 

## Set your timezone
The config file .emilerc also allows you to set your timezone. If not set, it will try to figure it out itself with the $TZ environment variable. If none of those options are set, it will fallback to UTC. <br> 
<br>
To set your timezone with emile, run the following command (locale needs to follow IANA timezone convention): <br> 
`emile set config locale Europe\London` <br> 

## Show configuration
You can print the content of your configuration living in .emilerc with the following command:<br>
`emile conf` <br> 

## Diagnose configuration problems
Sometimes it can happen that modifying manually your configuration some stuff might get messed up... for this reason I created a command called `doctor` which tries to diagnose what's wrong with your configuration. You can diagnose your configuration with the following command: <br> 
`emile doctor` <br> 

## Remove configuration
You can remove the current .emilerc configuration with the following command:
`emile purge`

## List all the posts for a blog
You can list all the posts for a registered blog using the following command:
`emile posts <blog_label>`

## Edit a blog post
You can edit blog posts that you previously created with the following command:
`emile edit <blog_label> <post_title|post_folder_name> [-e none|/editor]`

The post will be open for edit with your preferred text editor.
Precedence is: inline through -e > .emilerc > $EDITOR

## Remove a blog post
You can remove a blog post that you previously created with the following command:
`emile rm <blog_label> <post_title|post_folder_name> [-f]`

If the `rm` command is run without the `-f` parameter, it prompts for confirmation, otherwise it forces deletion.

## New features / Feedback
That's all for the moment, but there will probably be more features coming down the line, according to other needs I might have for my blogging. In case you are using emile for your blog, thank you and feel free to send me any suggestions or requests for new features. <br> 
 <br> 
<b>Happy blogging!</b>