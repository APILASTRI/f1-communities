# Normalized F1-communities
A novel approach to evaluate community detection algorithms on ground truth

Giulio Rossetti, Luca Pappalardo and Salvatore Rinzivillo
(CompleNet 2016)

Evaluating a community detection algorithm is a complex task due to the lack of a shared and universally accepted definition of community. In literature, one of the most common way to assess the performances of a community detection algorithm is to compare its output with given ground-truth communities by using computationally expensive metrics (i.e., Normalized Mutual Information). We proposed a novel approach aimed at evaluate the adherence of a community partition to the ground truth: our methodology provides more information than the state-of-the-art ones and is fast to compute on large-scale networks. By defining a classification problem on the real community label we compute an average F1-score that captures the level of approximation reached by network partitions obtained through community discovery algorithms w.r.t. ground-truth ones. Moreover, our approach allows for a visual inspection of the partition quality exploiting density scatter plots.

Instructions:

To execute, the following command line has to be used from the shell:

    python F1_communities.py community_file ground_truth_file [--plot output_filename] [--maxpts points_to_plot] [--title plot_title] 

Where:

    community_file: is the file containing the community identified by a Community Discovery algorithm;
    ground_truth_file: is the file containing the ground-truth community;
    output_filename: defines the plot filename (optional, if not specified the plot will not be generated);
    points_to_plot: defines the number of points to plot (optional – if not specified all the points will be plotted);
    plot_title: defines the plot title (optional).

File(s) Format:

The script expects as minimal inputs two text files containing community descriptions.
Each line of the input files should identify a single community as a list of node ids (the accepted separator are: tab, space, comma).

Community file example:
```python
1 [0,1,2,3]
2 [5,6,7,8]
3 [1,6,3]
```

In order to avoid biased evaluations be sure to comply with the following rules:
 - A community must be composed by at least 3 nodes.
 - No nested communities: a community must not be a proper subset of another community.