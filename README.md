# MYSQL Server
#### **login to MySQL server**
```shell
mysql -u root -pExpenseApp@1
```
1. **Select the database**:
```sql
show databases;
```


hari 
```sql
use transactions;

```
```sql
show tables;
```

In Jenkins, there are two main types of pipelines:

1. **Scripted Pipelines**: These are defined using a domain-specific language (DSL) based on Groovy. Scripted Pipelines are highly flexible and powerful, allowing complex workflows. They look something like this:

    ```groovy
    node {
        stage('Build') {
            echo 'Building...'
        }
        stage('Test') {
            echo 'Testing...'
        }
        stage('Deploy') {
            echo 'Deploying...'
        }
    }
    ```

2. **Declarative Pipelines**: These are more structured and simpler to read and write. They use a declarative syntax that defines a pipeline in a straightforward, hierarchical manner. Here’s an example:

    ```groovy
    pipeline {
        agent any
        stages {
            stage('Build') {
                steps {
                    echo 'Building...'
                }
            }
            stage('Test') {
                steps {
                    echo 'Testing...'
                }
            }
            stage('Deploy') {
                steps {
                    echo 'Deploying...'
                }
            }
        }
    }
    ```

Both types of pipelines are powerful, but the choice between them often depends on the complexity of your workflow and your preference for flexibility versus simplicity.

```bash
curl http://localhost:8080/transaction 
```