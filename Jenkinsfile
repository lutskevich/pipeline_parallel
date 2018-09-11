node{
	if (params.load_annul) {
						stage('load_annul'){ tasks {}
									sh 'sleep 5'
									sh 'echo load_annul'
						}
	}	    
	parallel job1: {
					if (params.aggregate) {
										stage('aggregate'){
													sh 'sleep 2'
													sh 'echo aggregate'
												
										}
					}
	},
	job2: {
			if (params.match) { 
								stage('match'){
												sh 'sleep 12'
												sh 'echo match'
												
								}
			}
	}
	if (params.hbase_to_hive) {
						stage('hbase_to_hive'){
										sh 'sleep 5'
										sh 'echo hbase_to_hive'
						}
	}
	parallel job1: {
					if (params.oracle_to_hive) {
										stage('oracle_to_hive'){
													sh 'sleep 2'
													sh 'echo oracle_to_hive'
										}
					}
	},
	job2: {
			if (params.mismatch_create) { 
								stage('mismatch_create'){
												sh 'sleep 12'
												sh 'echo mismatch_create'
								}
			}
	}
    if (params.clear_cache) {
						stage('clear_cache'){
									sh 'sleep 5'
									sh 'echo clear_cache'
						}
	}
}
