# dev_CitusRH7
Deployment and Workspace for CitusDB

#### Deploy v7.2

#### Upgrade from v7.2 to v8.x
  - Notes
    - [ Upgrade Info ](https://citus-doc.readthedocs.io/en/latest/admin_guide/upgrading_citus.html) <br/>
    - Do not attempt to upgrade both Citus and Postgres versions at once. If both upgrades are desired, upgrade Citus first.
      Also Citus 7.x is not compatible with Postgres 11. Before upgrading Postgres 10 to 11, be sure to follow the above steps to upgrade from Citus 7.x to 8.0.
    - On Every Node(Coordinator and workers)
      1. Backup Citus metadata in old server <br/>
      2. Configure new database instance to use Citus <br/>
      3. Stop old server <br/>
      4. Check upgrade compatibility <br/>
      5. Perform upgrade(like before but without the --check option) <br/>
      6. Start the new server <br/>
      7. Restore metadata <br/>
      8. Drop temporary metadata tables <br/>
      9. Restart sequences <br/>
     10. Register Triggers <br/>
     11. Set Dependencies  <br/>

#### Released Versiona (updates)s
  - v11.0
  - v10.2
  - v10.1
  - v10.0
  - v9.5
  - v9.4
  - v9.3
  - v9.2 
