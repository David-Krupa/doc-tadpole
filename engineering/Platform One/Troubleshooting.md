# Troubleshooting Deployment Issues

## Backend

### Python

If you find a problem dealing with FIPS or `hashlib.md5` in Python during deployment (likely seen in the logs of a K8s pod via Argo), please create an issue with Platform One immediately as this is not within our ability to resolve:

Example stacktrace:

```
Traceback (most recent call last):
  File "/home/appuser/manage.py", line 18, in <module>
    main()
  File "/home/appuser/manage.py", line 14, in main
    execute_from_command_line(sys.argv)
  File "/home/appuser/python-packages/django/core/management/__init__.py", line 419, in execute_from_command_line
    utility.execute()
  File "/home/appuser/python-packages/django/core/management/__init__.py", line 413, in execute
    self.fetch_command(subcommand).run_from_argv(self.argv)
  File "/home/appuser/python-packages/django/core/management/base.py", line 354, in run_from_argv
    self.execute(*args, **cmd_options)
  File "/home/appuser/python-packages/django/core/management/base.py", line 398, in execute
    output = self.handle(*args, **options)
  File "/home/appuser/python-packages/django/core/management/base.py", line 89, in wrapped
    res = handle_func(*args, **kwargs)
  File "/home/appuser/python-packages/django/core/management/commands/migrate.py", line 244, in handle
    post_migrate_state = executor.migrate(
  File "/home/appuser/python-packages/django/db/migrations/executor.py", line 117, in migrate
    state = self._migrate_all_forwards(state, plan, full_plan, fake=fake, fake_initial=fake_initial)
  File "/home/appuser/python-packages/django/db/migrations/executor.py", line 147, in _migrate_all_forwards
    state = self.apply_migration(state, migration, fake=fake, fake_initial=fake_initial)
  File "/home/appuser/python-packages/django/db/migrations/executor.py", line 230, in apply_migration
    migration_recorded = True
  File "/home/appuser/python-packages/django/db/backends/base/schema.py", line 118, in __exit__
    self.execute(sql)
  File "/home/appuser/python-packages/django/db/backends/base/schema.py", line 134, in execute
    sql = str(sql)
  File "/home/appuser/python-packages/django/db/backends/ddl_references.py", line 201, in __str__
    return self.template % self.parts
  File "/home/appuser/python-packages/django/db/backends/ddl_references.py", line 163, in __str__
    return self.create_fk_name(self.table, self.columns, suffix)
  File "/home/appuser/python-packages/django/db/backends/base/schema.py", line 1177, in create_fk_name
    return self.quote_name(self._create_index_name(*args, **kwargs))
  File "/home/appuser/python-packages/django/db/backends/base/schema.py", line 985, in _create_index_name
    hash_suffix_part = '%s%s' % (names_digest(table_name, *column_names, length=8), suffix)
  File "/home/appuser/python-packages/django/db/backends/utils.py", line 218, in names_digest
    h = hashlib.md5()
```