# Analysis_of_Large_Scale_Social_Networks
Repository for graph database project in NEO4J based on the public transportation dataset of the city of Zurich

#### PYTHON WITH NEO4J ON LOCAL MACHINE

from neo4j import GraphDatabase 
<br />
driver = GraphDatabase.driver("neo4j://localhost:7687", auth=("neo4j", "password"))
<br />
def retrieve_nodes(tx):
    for record in tx.run("MATCH (n) RETURN n"): print(record['n'])
<br />
with driver.session() as session: session.write_transaction(retrieve_nodes)
<br />
driver.close()
<br />
<br />
https://neo4j.com/docs/operations-manual/current/configuration/password-and-user-recovery/index.html
<br />
ALTER USER neo4j SET PASSWORD 'mynewpass'

<br />
<br />
#### SOURCES

Database: <br />
https://data.stadt-zuerich.ch/dataset/vbz_fahrzeiten_ogd_2018/download/Fahrzeiten_SOLL_IST_20181007_20181013.csv

Project set up and CSV import: <br />
https://neo4j.com/developer/desktop-csv-import/ <br />

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
