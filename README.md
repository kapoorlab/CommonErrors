# CommonErrors
A list of errors I have encountered, their reasons and solutions

Exception in thread "main" java.lang.IllegalArgumentException: loops not allowed
at org.jgrapht.graph.AbstractBaseGraph.addEdge(Unknown Source)

This happens while using Kalman FIlter when it tries to connect a source to a target, this error means that the source and the target have the same hascode, a way to fix this is to put this condition in your synchronized(graph) method.

synchronized (graph) {
// Add edge to the graph.
graph.addVertex(source);
graph.addVertex(target);
if(source.hashCode()!=target.hashCode()) {
final DefaultWeightedEdge edge = graph.addEdge(source, target);
final double cost = assignmentCosts.get(source);
graph.setEdgeWeight(edge, cost);
}
}

FOR git and Xcode path errors:

sudo xcode-select --switch /Library/Developer/CommandLineTools/
