# Changelog
All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [0.1.0] - 2025-10-22

### Added

- This CHANGELOG file compliant to 'Keep a Changelog' and 'Semantic versioning'.
- README file with a guide on how to use emile.
- POSIX compliance - Emile follows POSIX standards so that it can be executed under OS that offers a POSIX shell and removing any external dependencies.
- .emilerc config file to save preferences for a smoother management of Zola blogs and posts.
- Possibility to register a list of favourite blogs to edit (they must exist locally) through `emile set blogs <label> <path/to/posts>`.
- Possibility to set a favourite editor to edit blog posts through `emile set config editor <path/to/editor>.
- Possibility to set favourite locale following IANA timezone database conventions through `emile set config locale <IANA_tz>`.
- `new` command to create a new post for a specified blog.
- `posts` command to list all the posts of a blog.
- `edit` command to edit a blog post.
- `rm` command to remove a blog post.
- `conf` command to show the config (.emilerc residing in the user's home).
- `doctor` command to diagnose the config (.emilerc residing in the user's home).
- `purge` command to delete the config (.emilerc residing in the user's home).


[0.0.1]: https://github.com/sebcossu/emile/releases/tag/v0.1.0
