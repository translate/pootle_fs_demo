
Notes for Pootle FS Git demo
----------------------------


- Everybody has a working Pootle setup, right?
- [Install pootle_fs_git](http://docs.translatehouse.org/projects/pootle/en/latest/features/pootle_fs_install_plugins.html)
- [Setup a Pootle FS git project](http://docs.translatehouse.org/projects/pootle/en/latest/features/pootle_fs_add_project.html)

  - Choose **git** backend
  - Use **git@github.com:translate/pootle_fs_demo.git** URL
  - Specify **/<language_code>/<dir_path>/<filename>.<ext>** mapping
  - Add mapping for **es_ES**

- The demo itself:

  - ``fetch`` and ``sync`` to ensure we pulled the remote repo translations to Pootle
  - Translate something and ``sync`` (translations are auto-staged)
  - Translate something else and touch same string in repo, then ``state`` to see conflict

    - Explain conflict solving 4 possibilities
    - Run ``merge`` and ``sync`` (FS prevails, Pootle becomes suggestion)

  - Add new file in repo, ``fetch`` then ``sync``
  - Remove file in repo, ``rm`` then ``sync``
  - Changes in ``templates`` are not automatically synced to the project languages, so needs to be [done outside Pootle](http://docs.translatehouse.org/projects/pootle/en/latest/server/project_setup.html#updating-strings-for-existing-project) as before Pootle FS.
