# Versioning Data and Models

Data science teams face data management questions around versions of data and
machine learning models. How do we keep track of changes in data, source code,
and ML models together? What's the best way to organize and store variations of
these files and directories?

![](/img/data-ver-complex.png) _Exponential complexity of data science projects_

Another problem in the field has to do with bookkeeping: being able to identify
past research inputs and processes to understand results, for knowledge sharing
or for debugging.

**Data Version Control** (DVC) helps you organize data and models effectively,
and capture their versions with
[Git commits](https://git-scm.com/book/en/v2/Git-Basics-Recording-Changes-to-the-Repository).
It supports data _versioning through codification_: describing which datasets,
ML artifacts, etc. should be in the <abbr>workspace</abbr> at any given time.
DVC also provides mechanisms to cache different data contents, and to switch
between these versions.

![](/img/project-versions.png) _DVC matches the right versions of data to the
rest of your project._

DVC makes projects fully _reproducible_:
[Restore](/doc/command-reference/checkout) any project version and find the
corresponding data instantly. At the same time, the data stays with you — free
from Git hosting storage
[constraints](https://docs.github.com/en/free-pro-team@latest/github/managing-large-files/what-is-my-disk-quota).

This is achieved with special
[metafiles](/doc/user-guide/dvc-files-and-directories) that can be put in Git
instead of the actual data. And by storing unique data versions (preventing file
duplication) separate from the workspace. Now file names don't need to change,
because they can variable data. The result is a single immutable history for
data, code, models, etc. — a proper experiments journal.

> To learn how DVC looks and feels, try the
> [versioning tutorial](/doc/use-cases/versioning-data-and-model-files/tutorial)
> 👩‍💻. <br/> There are also other [guides](/doc/user-guide) and
> [references](/doc/command-reference) that explain DVC in detail.

Benefits of our approach include:

- **Lightweight**: DVC is a
  [free](https://github.com/iterative/dvc/blob/master/LICENSE), open-source
  [command line](/doc/command-reference) tool that doesn't require databases,
  servers, or any other special services.

- **Consistency**: Keep your projects readable with stable file names. No need
  for complicated paths like `data/20190922/labels_v7_final` or for constantly
  editing these in source code.

- **Efficient data management**: Use a cost-effective on-premises or cloud
  storage of your choice for your data and ML models. DVC
  [optimizes](/doc/user-guide/large-dataset-optimization) data storage and
  transfers.

- **Collaboration**: Easily distribute your project development and share its
  data [internally](/doc/use-cases/shared-development-server) and
  [remotely](/doc/use-cases/sharing-data-and-model-files), or
  [reuse](/doc/start/data-access) it in other places.

- **Data compliance**: Review data modification attempts as Git
  [pull requests](https://www.dummies.com/web-design-development/what-are-github-pull-requests/).
  Audit this process later to learn when data or model versions were approved,
  and why.

- **GitOps**: Connect your data science projects with the Git-powered universe.
  Git workflows open the door to advanced tools such as continuous integration
  (like [CML](https://cml.dev/) CI/CD), specialized patterns such as
  [data registries](/doc/use-cases/data-registries), and other best practices.

In summary, data science and machine learning are iterative processes where the
lifecycles of data, models, and code happen at different paces. DVC helps you
define, manage, and enforce them.

And this is only the beginning. DVC comes with other [features](/features)
specific to data science out-of-the-box. Build, run, and versioning
[data pipelines](/doc/command-reference/dag), manage
[experiments](/doc/start/experiments) effectively, and more!
