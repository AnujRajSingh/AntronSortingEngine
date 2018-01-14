 ## A distributed Parallel External Merge Sort
 First Iteration
 How this works?
Readers read from the input files into buffers, which are sorted
by Sorters. Each sorted buffer is then passed to a Distributor,
which splits the buffer into a sorted chunk per
node and sends each chunk to its corresponding node.
Once received, these sorted chunks are heap-sorted by
software elements called Heapers in batches and each
resulting sorted batch is written to an intermediate file
on disk. In the second phase, software elements called
Mergers merge-sort the intermediate files on a given disk
into a single sorted output file.
