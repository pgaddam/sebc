```
{
  "timestamp" : "2017-03-22T20:05:11.387Z",
  "clusters" : [ {
    "name" : "pgaddam",
    "version" : "CDH5",
    "services" : [ {
      "name" : "zookeeper",
      "type" : "ZOOKEEPER",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "SERVER",
          "items" : [ {
            "name" : "zookeeper_server_java_heapsize",
            "value" : "824180736"
          } ]
        } ],
        "items" : [ ]
      },
      "roles" : [ {
        "name" : "zookeeper-SERVER-1fbb184d3d4539b7efff3c9a5ba322c8",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "e97ed44f-e635-482e-bdc9-e7cce5f9d359"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "15z77o8ytuw3h3x1pudkiuznc"
          }, {
            "name" : "serverId",
            "value" : "1"
          } ]
        }
      }, {
        "name" : "zookeeper-SERVER-411e69a54956c7c3a05a64fadb5cdaee",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "06e8bdc2-34ae-485b-bbd7-528e1af71a15"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "8jc95jrdq00ezha4tlu3v8cmt"
          }, {
            "name" : "serverId",
            "value" : "2"
          } ]
        }
      }, {
        "name" : "zookeeper-SERVER-bdf4c6870b89d58197e3b0d17647bdc4",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "5a5873ff-912b-4e34-98b0-966de1a0a4a8"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "9df81xgvu6q5em6rn9jv9qfpd"
          }, {
            "name" : "serverId",
            "value" : "3"
          } ]
        }
      } ],
      "displayName" : "ZooKeeper"
    }, {
      "name" : "oozie",
      "type" : "OOZIE",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "OOZIE_SERVER",
          "items" : [ {
            "name" : "oozie_database_host",
            "value" : "ip-172-31-10-79.us-west-1.compute.internal"
          }, {
            "name" : "oozie_database_password",
            "value" : "oozie1@Training"
          }, {
            "name" : "oozie_database_type",
            "value" : "mysql"
          }, {
            "name" : "oozie_database_user",
            "value" : "oozie"
          } ]
        } ],
        "items" : [ {
          "name" : "hive_service",
          "value" : "hive"
        }, {
          "name" : "mapreduce_yarn_service",
          "value" : "yarn"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "oozie-OOZIE_SERVER-1fbb184d3d4539b7efff3c9a5ba322c8",
        "type" : "OOZIE_SERVER",
        "hostRef" : {
          "hostId" : "e97ed44f-e635-482e-bdc9-e7cce5f9d359"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "1sui0f014xqkkuoclbhpg3wn1"
          } ]
        }
      } ],
      "displayName" : "Oozie"
    }, {
      "name" : "hue",
      "type" : "HUE",
      "config" : {
        "roleTypeConfigs" : [ ],
        "items" : [ {
          "name" : "database_host",
          "value" : "ip-172-31-10-79.us-west-1.compute.internal"
        }, {
          "name" : "database_password",
          "value" : "hue1@Training"
        }, {
          "name" : "database_type",
          "value" : "mysql"
        }, {
          "name" : "hive_service",
          "value" : "hive"
        }, {
          "name" : "hue_webhdfs",
          "value" : "hdfs-HTTPFS-1fbb184d3d4539b7efff3c9a5ba322c8"
        }, {
          "name" : "oozie_service",
          "value" : "oozie"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hue-HUE_SERVER-1fbb184d3d4539b7efff3c9a5ba322c8",
        "type" : "HUE_SERVER",
        "hostRef" : {
          "hostId" : "e97ed44f-e635-482e-bdc9-e7cce5f9d359"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "h4czywvtuzgo84b8mmmb30ze"
          }, {
            "name" : "secret_key",
            "value" : "vzXO47pKhrvWjGyKoNrQZ1HAA4RZmb"
          } ]
        }
      }, {
        "name" : "hue-HUE_SERVER-bdf4c6870b89d58197e3b0d17647bdc4",
        "type" : "HUE_SERVER",
        "hostRef" : {
          "hostId" : "5a5873ff-912b-4e34-98b0-966de1a0a4a8"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "2ej7370k2qm5rb40qe24jguyq"
          }, {
            "name" : "secret_key",
            "value" : "WDuLzn0omQD5eW0KS3Z3BJ1f9jLuat"
          } ]
        }
      } ],
      "displayName" : "Hue"
    }, {
      "name" : "hdfs",
      "type" : "HDFS",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "BALANCER",
          "items" : [ {
            "name" : "balancer_java_heapsize",
            "value" : "824180736"
          } ]
        }, {
          "roleType" : "DATANODE",
          "items" : [ {
            "name" : "datanode_java_heapsize",
            "value" : "1073741824"
          }, {
            "name" : "dfs_data_dir_list",
            "value" : "/dfs/dn,/data/0/dfs/dn"
          }, {
            "name" : "dfs_datanode_du_reserved",
            "value" : "3219866009"
          }, {
            "name" : "dfs_datanode_failed_volumes_tolerated",
            "value" : "1"
          }, {
            "name" : "dfs_datanode_max_locked_memory",
            "value" : "4294967296"
          }, {
            "name" : "rm_cpu_shares",
            "value" : "200"
          }, {
            "name" : "rm_io_weight",
            "value" : "100"
          } ]
        }, {
          "roleType" : "GATEWAY",
          "items" : [ {
            "name" : "dfs_client_use_trash",
            "value" : "true"
          } ]
        }, {
          "roleType" : "JOURNALNODE",
          "items" : [ {
            "name" : "dfs_journalnode_edits_dir",
            "value" : "/data/0/jn"
          } ]
        }, {
          "roleType" : "NAMENODE",
          "items" : [ {
            "name" : "dfs_name_dir_list",
            "value" : "/dfs/nn,/data/0/dfs/nn"
          }, {
            "name" : "dfs_namenode_servicerpc_address",
            "value" : "8022"
          }, {
            "name" : "namenode_java_heapsize",
            "value" : "1073741824"
          } ]
        }, {
          "roleType" : "SECONDARYNAMENODE",
          "items" : [ {
            "name" : "fs_checkpoint_dir_list",
            "value" : "/dfs/snn"
          }, {
            "name" : "secondary_namenode_java_heapsize",
            "value" : "1073741824"
          } ]
        } ],
        "items" : [ {
          "name" : "dfs_ha_fencing_cloudera_manager_secret_key",
          "value" : "p8i7BfqEkLRXjIomuyytap829BCLyu"
        }, {
          "name" : "dfs_ha_fencing_methods",
          "value" : "shell(true)"
        }, {
          "name" : "fc_authorization_secret_key",
          "value" : "nbtnVNVGT8sJZb2SPbQltgzjtu4rPc"
        }, {
          "name" : "http_auth_signature_secret",
          "value" : "r4qL7wtlEBIvLnXBFm3NYp7IyCqS04"
        }, {
          "name" : "rm_dirty",
          "value" : "false"
        }, {
          "name" : "rm_last_allocation_percentage",
          "value" : "10"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hdfs-BALANCER-bdf4c6870b89d58197e3b0d17647bdc4",
        "type" : "BALANCER",
        "hostRef" : {
          "hostId" : "5a5873ff-912b-4e34-98b0-966de1a0a4a8"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hdfs-DATANODE-3bd66fe6107e61426498289028d9e4e6",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "4db52203-6ba9-463c-88d9-8fb39f1bc820"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "2gwqx21z2ifh2ispu457q6svw"
          } ]
        }
      }, {
        "name" : "hdfs-DATANODE-411e69a54956c7c3a05a64fadb5cdaee",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "06e8bdc2-34ae-485b-bbd7-528e1af71a15"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "34e8c2mqpez3a9n8o9xjv9k4d"
          } ]
        }
      }, {
        "name" : "hdfs-DATANODE-e5a2aabc6dc2a9832ce98c4f4d66d45d",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "01c4355d-d065-44b3-8aad-adc55a055fe1"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "1oz5cfw6uthmqyz1pbp5l7xd4"
          } ]
        }
      }, {
        "name" : "hdfs-FAILOVERCONTROLLER-1fbb184d3d4539b7efff3c9a5ba322c8",
        "type" : "FAILOVERCONTROLLER",
        "hostRef" : {
          "hostId" : "e97ed44f-e635-482e-bdc9-e7cce5f9d359"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "crckwvy01timtl3rpr1r0adrx"
          } ]
        }
      }, {
        "name" : "hdfs-FAILOVERCONTROLLER-bdf4c6870b89d58197e3b0d17647bdc4",
        "type" : "FAILOVERCONTROLLER",
        "hostRef" : {
          "hostId" : "5a5873ff-912b-4e34-98b0-966de1a0a4a8"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "5jcx2t1q8ngdvbnhuzcnyexxe"
          } ]
        }
      }, {
        "name" : "hdfs-HTTPFS-1fbb184d3d4539b7efff3c9a5ba322c8",
        "type" : "HTTPFS",
        "hostRef" : {
          "hostId" : "e97ed44f-e635-482e-bdc9-e7cce5f9d359"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "ewgiqgyvmgjt8e6u02scwfgk9"
          } ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-1fbb184d3d4539b7efff3c9a5ba322c8",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "e97ed44f-e635-482e-bdc9-e7cce5f9d359"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "1nuf6fshw9dgxtsx7xeushn6e"
          } ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-411e69a54956c7c3a05a64fadb5cdaee",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "06e8bdc2-34ae-485b-bbd7-528e1af71a15"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "b0jipakw4w5m2v3d30grutyap"
          } ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-bdf4c6870b89d58197e3b0d17647bdc4",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "5a5873ff-912b-4e34-98b0-966de1a0a4a8"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "bfdww3co6lgv4wsgzfn90iqmw"
          } ]
        }
      }, {
        "name" : "hdfs-NAMENODE-1fbb184d3d4539b7efff3c9a5ba322c8",
        "type" : "NAMENODE",
        "hostRef" : {
          "hostId" : "e97ed44f-e635-482e-bdc9-e7cce5f9d359"
        },
        "config" : {
          "items" : [ {
            "name" : "autofailover_enabled",
            "value" : "true"
          }, {
            "name" : "dfs_federation_namenode_nameservice",
            "value" : "nameservice2"
          }, {
            "name" : "dfs_namenode_quorum_journal_name",
            "value" : "nameservice2"
          }, {
            "name" : "namenode_id",
            "value" : "68"
          }, {
            "name" : "role_jceks_password",
            "value" : "5ejud1tz08dh4zy7lmchh2ja8"
          } ]
        }
      }, {
        "name" : "hdfs-NAMENODE-bdf4c6870b89d58197e3b0d17647bdc4",
        "type" : "NAMENODE",
        "hostRef" : {
          "hostId" : "5a5873ff-912b-4e34-98b0-966de1a0a4a8"
        },
        "config" : {
          "items" : [ {
            "name" : "autofailover_enabled",
            "value" : "true"
          }, {
            "name" : "dfs_federation_namenode_nameservice",
            "value" : "nameservice2"
          }, {
            "name" : "dfs_namenode_quorum_journal_name",
            "value" : "nameservice2"
          }, {
            "name" : "namenode_id",
            "value" : "53"
          }, {
            "name" : "role_jceks_password",
            "value" : "60u1bjsycvlxwnv97n8cqum7h"
          } ]
        }
      }, {
        "name" : "hdfs-NFSGATEWAY-1fbb184d3d4539b7efff3c9a5ba322c8",
        "type" : "NFSGATEWAY",
        "hostRef" : {
          "hostId" : "e97ed44f-e635-482e-bdc9-e7cce5f9d359"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "63koqp71aq49sct0wroojti5s"
          } ]
        }
      }, {
        "name" : "hdfs-NFSGATEWAY-bdf4c6870b89d58197e3b0d17647bdc4",
        "type" : "NFSGATEWAY",
        "hostRef" : {
          "hostId" : "5a5873ff-912b-4e34-98b0-966de1a0a4a8"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "a9prd36686dt6qgzicfqn6qha"
          } ]
        }
      } ],
      "displayName" : "HDFS"
    }, {
      "name" : "yarn",
      "type" : "YARN",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "GATEWAY",
          "items" : [ {
            "name" : "mapred_reduce_tasks",
            "value" : "6"
          }, {
            "name" : "mapred_submit_replication",
            "value" : "1"
          } ]
        }, {
          "roleType" : "NODEMANAGER",
          "items" : [ {
            "name" : "rm_cpu_shares",
            "value" : "1800"
          }, {
            "name" : "rm_io_weight",
            "value" : "900"
          }, {
            "name" : "yarn_nodemanager_heartbeat_interval_ms",
            "value" : "100"
          }, {
            "name" : "yarn_nodemanager_local_dirs",
            "value" : "/yarn/nm,/data/0/yarn/nm"
          }, {
            "name" : "yarn_nodemanager_log_dirs",
            "value" : "/yarn/container-logs,/data/0/yarn/container-logs"
          }, {
            "name" : "yarn_nodemanager_resource_cpu_vcores",
            "value" : "3"
          }, {
            "name" : "yarn_nodemanager_resource_memory_mb",
            "value" : "5745"
          } ]
        }, {
          "roleType" : "RESOURCEMANAGER",
          "items" : [ {
            "name" : "yarn_scheduler_maximum_allocation_mb",
            "value" : "5745"
          }, {
            "name" : "yarn_scheduler_maximum_allocation_vcores",
            "value" : "3"
          } ]
        } ],
        "items" : [ {
          "name" : "hdfs_service",
          "value" : "hdfs"
        }, {
          "name" : "rm_dirty",
          "value" : "false"
        }, {
          "name" : "rm_last_allocation_percentage",
          "value" : "90"
        }, {
          "name" : "yarn_service_cgroups",
          "value" : "false"
        }, {
          "name" : "yarn_service_lce_always",
          "value" : "false"
        }, {
          "name" : "zk_authorization_secret_key",
          "value" : "lTYRnKgqmePyk4HZnWw5fMEmW7Z7pH"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "yarn-GATEWAY-1fbb184d3d4539b7efff3c9a5ba322c8",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "e97ed44f-e635-482e-bdc9-e7cce5f9d359"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "yarn-GATEWAY-bdf4c6870b89d58197e3b0d17647bdc4",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "5a5873ff-912b-4e34-98b0-966de1a0a4a8"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "yarn-JOBHISTORY-1fbb184d3d4539b7efff3c9a5ba322c8",
        "type" : "JOBHISTORY",
        "hostRef" : {
          "hostId" : "e97ed44f-e635-482e-bdc9-e7cce5f9d359"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "cbbjey9ci4cczpegst5e4rkr6"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-3bd66fe6107e61426498289028d9e4e6",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "4db52203-6ba9-463c-88d9-8fb39f1bc820"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "1om6d5c2s14lwbgv6xjfytq55"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-411e69a54956c7c3a05a64fadb5cdaee",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "06e8bdc2-34ae-485b-bbd7-528e1af71a15"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "9dimsjmapei5pelfctu21ap81"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-e5a2aabc6dc2a9832ce98c4f4d66d45d",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "01c4355d-d065-44b3-8aad-adc55a055fe1"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "22rbqq3f7zwyx2i69gcjjb555"
          } ]
        }
      }, {
        "name" : "yarn-RESOURCEMANAGER-1fbb184d3d4539b7efff3c9a5ba322c8",
        "type" : "RESOURCEMANAGER",
        "hostRef" : {
          "hostId" : "e97ed44f-e635-482e-bdc9-e7cce5f9d359"
        },
        "config" : {
          "items" : [ {
            "name" : "rm_id",
            "value" : "59"
          }, {
            "name" : "role_jceks_password",
            "value" : "4yjkp35dgt8c3xek5ytg85jeu"
          } ]
        }
      } ],
      "displayName" : "YARN (MR2 Included)"
    }, {
      "name" : "hive",
      "type" : "HIVE",
      "config" : {
        "roleTypeConfigs" : [ {
          "roleType" : "HIVEMETASTORE",
          "items" : [ {
            "name" : "hive_metastore_java_heapsize",
            "value" : "1592786944"
          }, {
            "name" : "hive_metastore_server_max_message_size",
            "value" : "159278694"
          } ]
        }, {
          "roleType" : "HIVESERVER2",
          "items" : [ {
            "name" : "hiveserver2_java_heapsize",
            "value" : "824180736"
          }, {
            "name" : "hiveserver2_spark_driver_memory",
            "value" : "966367641"
          }, {
            "name" : "hiveserver2_spark_executor_cores",
            "value" : "4"
          }, {
            "name" : "hiveserver2_spark_executor_memory",
            "value" : "3934152294"
          }, {
            "name" : "hiveserver2_spark_yarn_driver_memory_overhead",
            "value" : "102"
          }, {
            "name" : "hiveserver2_spark_yarn_executor_memory_overhead",
            "value" : "662"
          } ]
        } ],
        "items" : [ {
          "name" : "hive_metastore_database_host",
          "value" : "ip-172-31-10-79.us-west-1.compute.internal"
        }, {
          "name" : "hive_metastore_database_password",
          "value" : "hive1@Training"
        }, {
          "name" : "mapreduce_yarn_service",
          "value" : "yarn"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hive-GATEWAY-1fbb184d3d4539b7efff3c9a5ba322c8",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "e97ed44f-e635-482e-bdc9-e7cce5f9d359"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-GATEWAY-bdf4c6870b89d58197e3b0d17647bdc4",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "5a5873ff-912b-4e34-98b0-966de1a0a4a8"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-HIVEMETASTORE-1fbb184d3d4539b7efff3c9a5ba322c8",
        "type" : "HIVEMETASTORE",
        "hostRef" : {
          "hostId" : "e97ed44f-e635-482e-bdc9-e7cce5f9d359"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "5psxt5x2t2czslu2p8trgkp9z"
          } ]
        }
      }, {
        "name" : "hive-HIVEMETASTORE-bdf4c6870b89d58197e3b0d17647bdc4",
        "type" : "HIVEMETASTORE",
        "hostRef" : {
          "hostId" : "5a5873ff-912b-4e34-98b0-966de1a0a4a8"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "cb2uw4vph8ywlto2l6rn0dsfw"
          } ]
        }
      }, {
        "name" : "hive-HIVESERVER2-1fbb184d3d4539b7efff3c9a5ba322c8",
        "type" : "HIVESERVER2",
        "hostRef" : {
          "hostId" : "e97ed44f-e635-482e-bdc9-e7cce5f9d359"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "3ao1j6akzs074ikhlpi5bcysb"
          } ]
        }
      }, {
        "name" : "hive-HIVESERVER2-bdf4c6870b89d58197e3b0d17647bdc4",
        "type" : "HIVESERVER2",
        "hostRef" : {
          "hostId" : "5a5873ff-912b-4e34-98b0-966de1a0a4a8"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "96nd8apzfk193l08er61xyhhi"
          } ]
        }
      }, {
        "name" : "hive-WEBHCAT-1fbb184d3d4539b7efff3c9a5ba322c8",
        "type" : "WEBHCAT",
        "hostRef" : {
          "hostId" : "e97ed44f-e635-482e-bdc9-e7cce5f9d359"
        },
        "config" : {
          "items" : [ {
            "name" : "hive_webhcat_secret_key",
            "value" : "fx4XBvn9aYQba6g68qNhGQmThe5aDw"
          }, {
            "name" : "role_jceks_password",
            "value" : "6u1dvj1vvuj9obflrb1i5fr9e"
          } ]
        }
      } ],
      "displayName" : "Hive"
    } ]
  } ],
  "hosts" : [ {
    "hostId" : "5a5873ff-912b-4e34-98b0-966de1a0a4a8",
    "ipAddress" : "172.31.10.79",
    "hostname" : "ip-172-31-10-79.us-west-1.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "06e8bdc2-34ae-485b-bbd7-528e1af71a15",
    "ipAddress" : "172.31.11.9",
    "hostname" : "ip-172-31-11-9.us-west-1.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "e97ed44f-e635-482e-bdc9-e7cce5f9d359",
    "ipAddress" : "172.31.2.148",
    "hostname" : "ip-172-31-2-148.us-west-1.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "01c4355d-d065-44b3-8aad-adc55a055fe1",
    "ipAddress" : "172.31.4.97",
    "hostname" : "ip-172-31-4-97.us-west-1.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "4db52203-6ba9-463c-88d9-8fb39f1bc820",
    "ipAddress" : "172.31.6.199",
    "hostname" : "ip-172-31-6-199.us-west-1.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  } ],
  "users" : [ {
    "name" : "__cloudera_internal_user__1b8d7812-61cb-4f59-8d0c-5ab1e6ca8cc0",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "06c3199b311bef7db7ab166d41faadc9e814644915bd3ccf2264a656051b3391",
    "pwSalt" : -7900868146551614227,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__b3f61305-2f42-40ff-a651-7e96f970417e",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "923854c11a141cf237029d986b42c4c048d6e1bf007fba715377365d79c23a8f",
    "pwSalt" : -8388171262412115152,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-EVENTSERVER-bdf4c6870b89d58197e3b0d17647bdc4",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "4897f3a6789bde5246a823a8c5fcf8da0ca5b3e2b91d17653e704fc197e4f677",
    "pwSalt" : -3701373822398472975,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-HOSTMONITOR-bdf4c6870b89d58197e3b0d17647bdc4",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "c1e0547cda93c887e2ec09227a5950a863ef8b573e62380ec7c94fd1fdbd14b4",
    "pwSalt" : -2513328957363130502,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-REPORTSMANAGER-bdf4c6870b89d58197e3b0d17647bdc4",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "0ff2862652543620ec85b17c3e66debb6e65531259dd67e934e047249a6763cd",
    "pwSalt" : -2592444346355486086,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-SERVICEMONITOR-bdf4c6870b89d58197e3b0d17647bdc4",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "7fe9811a796aac1e8f7c7974b21eb34c7321e93c5bd193bfd2b8dd97e17af640",
    "pwSalt" : -2545423143829268667,
    "pwLogin" : true
  }, {
    "name" : "admin",
    "roles" : [ "ROLE_LIMITED" ],
    "pwHash" : "c1883a37568990856f70b900c8a0e9a68a2eedd59bf9021450e00d7f03ec0aa5",
    "pwSalt" : 8365207547863414330,
    "pwLogin" : true
  }, {
    "name" : "minotaur",
    "roles" : [ "ROLE_CONFIGURATOR" ],
    "pwHash" : "821ec3fee8f4aeb460308564aec790451e3412676ea01bbc7c99f807171a945c",
    "pwSalt" : 9160978974540016923,
    "pwLogin" : true
  }, {
    "name" : "pgaddam",
    "roles" : [ "ROLE_ADMIN" ],
    "pwHash" : "456c0871206f63590cc90561cb340e57e94228437db50d3585245dfbbc25eddf",
    "pwSalt" : 4317310115755132988,
    "pwLogin" : true
  } ],
  "versionInfo" : {
    "version" : "5.9.1",
    "buildUser" : "jenkins",
    "buildTimestamp" : "20170112-1158",
    "gitHash" : "a66d8bbdbe8bc3ee54235e55423f2f76c7d9f3b1",
    "snapshot" : false
  },
  "managementService" : {
    "name" : "mgmt",
    "type" : "MGMT",
    "config" : {
      "roleTypeConfigs" : [ {
        "roleType" : "EVENTSERVER",
        "items" : [ {
          "name" : "event_server_heapsize",
          "value" : "824180736"
        } ]
      }, {
        "roleType" : "HOSTMONITOR",
        "items" : [ {
          "name" : "firehose_heapsize",
          "value" : "824180736"
        }, {
          "name" : "firehose_non_java_memory_bytes",
          "value" : "1071644672"
        } ]
      }, {
        "roleType" : "REPORTSMANAGER",
        "items" : [ {
          "name" : "headlamp_database_host",
          "value" : "ip-172-31-10-79.us-west-1.compute.internal"
        }, {
          "name" : "headlamp_database_name",
          "value" : "rman"
        }, {
          "name" : "headlamp_database_password",
          "value" : "rman1@Training"
        }, {
          "name" : "headlamp_database_user",
          "value" : "rman"
        }, {
          "name" : "headlamp_heapsize",
          "value" : "824180736"
        } ]
      }, {
        "roleType" : "SERVICEMONITOR",
        "items" : [ {
          "name" : "firehose_heapsize",
          "value" : "824180736"
        }, {
          "name" : "firehose_non_java_memory_bytes",
          "value" : "1071644672"
        } ]
      } ],
      "items" : [ ]
    },
    "roles" : [ {
      "name" : "mgmt-ALERTPUBLISHER-bdf4c6870b89d58197e3b0d17647bdc4",
      "type" : "ALERTPUBLISHER",
      "hostRef" : {
        "hostId" : "5a5873ff-912b-4e34-98b0-966de1a0a4a8"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "dp3am0vt0o7qj83icg1ns1ojp"
        } ]
      }
    }, {
      "name" : "mgmt-EVENTSERVER-bdf4c6870b89d58197e3b0d17647bdc4",
      "type" : "EVENTSERVER",
      "hostRef" : {
        "hostId" : "5a5873ff-912b-4e34-98b0-966de1a0a4a8"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "3ifpfknnnljgpyxtxorhrcih7"
        } ]
      }
    }, {
      "name" : "mgmt-HOSTMONITOR-bdf4c6870b89d58197e3b0d17647bdc4",
      "type" : "HOSTMONITOR",
      "hostRef" : {
        "hostId" : "5a5873ff-912b-4e34-98b0-966de1a0a4a8"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "bk77mcwgotzk0n2nwm6vnkux8"
        } ]
      }
    }, {
      "name" : "mgmt-REPORTSMANAGER-bdf4c6870b89d58197e3b0d17647bdc4",
      "type" : "REPORTSMANAGER",
      "hostRef" : {
        "hostId" : "5a5873ff-912b-4e34-98b0-966de1a0a4a8"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "8fi3yqiq8s770sdz9qk632l49"
        } ]
      }
    }, {
      "name" : "mgmt-SERVICEMONITOR-bdf4c6870b89d58197e3b0d17647bdc4",
      "type" : "SERVICEMONITOR",
      "hostRef" : {
        "hostId" : "5a5873ff-912b-4e34-98b0-966de1a0a4a8"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "7w9ojn8hu5xii6t6augsw2cd9"
        } ]
      }
    } ],
    "displayName" : "Cloudera Management Service"
  },
  "managerSettings" : {
    "items" : [ {
      "name" : "CLUSTER_STATS_START",
      "value" : "10/21/2012 16:20"
    }, {
      "name" : "PUBLIC_CLOUD_STATUS",
      "value" : "ON_PUBLIC_CLOUD"
    }, {
      "name" : "REMOTE_PARCEL_REPO_URLS",
      "value" : "https://archive.cloudera.com/cdh5/parcels/{latest_supported}/,https://archive.cloudera.com/cdh4/parcels/latest/,https://archive.cloudera.com/impala/parcels/latest/,https://archive.cloudera.com/search/parcels/latest/,https://archive.cloudera.com/accumulo/parcels/1.4/,https://archive.cloudera.com/accumulo-c5/parcels/latest/,https://archive.cloudera.com/kafka/parcels/latest/,https://archive.cloudera.com/navigator-keytrustee5/parcels/latest/,https://archive.cloudera.com/spark/parcels/latest/,https://archive.cloudera.com/sqoop-connectors/parcels/latest/"
    } ]
  }
}
```