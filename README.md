# dbt-tutorial
[https://docs.getdbt.com/guides/manual-install?step=1](https://docs.getdbt.com/guides/manual-install?step=1)

### Notes
#### Pre-reqs:
* Install dbt along with package.
* Create a project and set it up in GCP (credentials, load data, etc..)

#### Initial setup
Create repo

Activate environment, check dbt version to make sure you have it, initialize project
```
dbt_env
dbt --version
dbt init jaffle_shop
```
> Configure profile:  https://docs.getdbt.com/docs/configure-your-profile

Options selected:
* bigquery
* service_account
* entered path/to/bq/keyfile.json **must enter full path, `~` did not work** see the screenshot in [step 4](https://docs.getdbt.com/guides/manual-install?step=4)
* entered project, dataset, threads, timeout, and lcation information

> Tutorial differs, you don't have to create your own `profiles.yml` file. The `init` command took care of that (at least for the first run)

Check that `dbt run` works with the examples

### Building First Models
Create a new branch

Create customers.sql model

`dbt run`

**NOTE:** After the first created customer table, `dbt run` threw an error because customers existed as table. Then, after updating `customers.sql` with refs to the stg tables, `dbt run` did not need a `--full-refresh` to update the view into a table.


