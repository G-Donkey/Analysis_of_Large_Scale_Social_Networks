# Analysis_of_Large_Scale_Social_Networks
Repository for graph database project in NEO4J based on the public transportation dataset of the city of Zurich

### PYTHON WITH NEO4J ON LOCAL MACHINE
    
    # Connect, read and write to graph on NEO4J
    from neo4j import GraphDatabase 

    driver = GraphDatabase.driver("neo4j://localhost:7687", auth=("neo4j", "password"))

    def retrieve_nodes(tx):
        for record in tx.run("MATCH (n) RETURN n"): print(record['n'])

    with driver.session() as session: session.write_transaction(retrieve_nodes)

    driver.close()
ALTER USER neo4j SET PASSWORD '*'
<br />
https://neo4j.com/docs/operations-manual/current/configuration/password-and-user-recovery/index.html



### SOURCES

Database: <br />
https://data.stadt-zuerich.ch/dataset/vbz_fahrzeiten_ogd_2018/download/Fahrzeiten_SOLL_IST_20181007_20181013.csv

Project set up and CSV import: <br />
https://neo4j.com/developer/desktop-csv-import/ <br />

Tutorials: <br />
https://neo4j.com/video/bite-sized-neo4j-for-data-scientists/

Variables handling: <br />
https://neo4j.com/docs/cypher-manual/current/functions/scalar/#functions-toboolean <br />

Spacial Coordinates: <br />
https://neo4j.com/docs/cypher-manual/current/functions/spatial/ <br />
https://neo4j.com/blog/building-spatial-search-algorithms-neo4j/

Transport graphs: <br />
http://blog.bruggen.com/2015/11/loading-general-transport-feed-spec.html <br />
http://blog.bruggen.com/2015/11/querying-gtfs-data-using-neo4j-23-part.html <br />
http://blog.bruggen.com/2015/03/hidden-graphgems-revisited-22-meta-graph.html

Weights: <br />
http://semanticgeek.com/graph/exploring-the-different-types-of-weights-in-a-connected-graph/

Indexes and constraints: <br />
https://dzone.com/articles/neo4j-indexes-match-merge

Graphs in Jupyter Notebook: <br />
https://medium.com/@technologydata25/connect-neo4j-to-jupyter-notebook-c178f716d6d5

Create maps:<br />
https://github.com/stellasia/neomap/releases
https://medium.com/neo4j/introducing-neomap-a-neo4j-desktop-application-for-spatial-data-3e14aad59db2
