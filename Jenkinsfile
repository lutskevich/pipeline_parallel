pipeline {
    agent any
    stages {
		stage('load_annul') {
                    steps {
						sleep 2
                        echo "load_annul DONE"
                    }
                }
        stage('Parallel Stages') {
            parallel {
                stage('aggregate') {
                    steps {
						sleep 2
                        echo "aggregate DONE"
                    }
                }
                stage('match') {
                    steps {
						sleep 8
                        echo "match DONE"
                    }
                }
            }
        }
    }
}
