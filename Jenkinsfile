pipeline {
  agent any
  stages {
    stage('load_annul') {
      parallel {
        stage('load_annul') {
          when {
            expression {
              return params.load_annul
            }

          }
          steps {
            sleep 2
            echo 'load_annul DONE'
          }
        }
        stage('error') {
          steps {
            mail(subject: 'Stage', body: 'Stage load_annul finished', from: 'Jenkins', to: 'viktor.lutskevich@firstlinesoftware.com')
          }
        }
      }
    }
    stage('Parallel Stages') {
      parallel {
        stage('aggregate') {
          when {
            expression {
              return params.aggregate
            }

          }
          steps {
            sleep 10
            echo 'aggregate DONE'
          }
        }
        stage('match') {
          when {
            expression {
              return params.match
            }

          }
          steps {
            sleep 10
            echo 'match DONE'
          }
        }
        stage('hbase_to_hive') {
          when {
            expression {
              return params.hbase_to_hive
            }

          }
          steps {
            sleep 5
            echo 'hbase_to_hive DONE'
          }
        }
      }
    }
    stage('oracle_to_hive') {
      when {
        expression {
          return params.oracle_to_hive
        }

      }
      steps {
        sleep 5
        echo 'oracle_to_hive DONE'
      }
    }
    stage('Parallel Stages 2') {
      parallel {
        stage('mismatch_create') {
          when {
            expression {
              return params.mismatch_create
            }

          }
          steps {
            sleep 5
            echo 'mismatch_create DONE'
          }
        }
        stage('clear_cache') {
          when {
            expression {
              return params.clear_cache
            }

          }
          steps {
            sleep 5
            echo 'clear_cache DONE'
          }
        }
      }
    }
    stage('knp_fc') {
      when {
        expression {
          return params.knp_fc
        }

      }
      steps {
        sleep 5
        echo 'knp_fc DONE'
        sh '''#!/bin/bash

echo -n "Start Stage $1"
sleep 5
echo ">> >> >> >> >> >> Stage $1 status: success. << << << << << <<";

exit 0'''
      }
    }
  }
}