# Augmenting Chinese Character Representations with Compositional Graph Learning

Chinese characters have semantic-rich compositional information in the form of radicals. While almost all previous research has applied CNNs to extract this compositional information at pixel level, lacking understanding on their geometric structure. Our work utilizes deep graph learning on a compact, graph-based representation of Chinese characters. This allows us to exploit temporal information within the strict stroke order used in writing characters. Our results show that our stroke-based model has potential for helping large-scale language models on some Chinese natural language understanding tasks. In particular, we demonstrate that our graph model produces more interpretable embeddings shown through word subtraction analogies and character embedding visualizations.
## Important Citation Note
This work is independent from Glyce, but borrows much of the code base written by Glyce in an effort to both reproduce their results and fairly compare our proposed stroke order method.

Meng, Y.; Wu, W.; Wang, F.; Li, X.; Nie, P.; Yin, F.; Li, M.;
Han, Q.; Sun, X.; and Li, J. 2019. Glyce: Glyph-vectors for
Chinese Character Representations. In _NIPS_, 2746–2757.

Their original repository can be found at https://github.com/ShannonAI/glyce.

Individual code files are annotated with specific credit details as well.

## File Organization Information
The graph dataset is provided under the two folder "zinode" and "zishp". Each of these folders contains a folder per Chinese character named with the character and given a unique id #. In "zinode", you'll find the adjacency matrix (A_#.npy) and spatial feature vector (X_#.npy) of the line segments. The temporal feature vectors are in strokeid_#.txt. "zishp" contains a #.shp file which can be loaded with the Geopandas library to see the characters as an image.  

The experiment code is provided under the "glyce/glyce" folder. Specifically, you will find the jupyter notebooks that produced the results in our paper under "glyce/glyce/experiments" and the python scripts that produced the case study visualizations under "glyce/glyce/bin/visualizer.py" and "graph_visualization.py". "graph_creator" contains the code for creating the graphs (graphsDictOrder.pickle) from the given stroke order dataset. All you need to do to run the code is to download the datasets described in the next section, change the configuration files' paths, and change the notebook's path hyperparameters.

## Data Not Included
The task data (Resume NER, CTB5 POS, PKU CWS, BQ Sentence Pair, and Fudan Sentiment Analysis) datasets are not provided here. You can download them through Glyce's GitHub: https://github.com/ShannonAI/glyce/blob/master/docs/dataset_download.md. The suggested download location is adacent to the outermost glyce folder.

The extra font data that Glyce requires to boost its performance is also not provided here. You can download them through Glyce's GitHub: https://github.com/ShannonAI/glyce/tree/master/glyce/fonts. The suggested download location is inside the innermost glyce folder.

## Contact 
Feel free to reach out to jasonwang1 [at] college [dot] harvard [dot] edu with any questions!

## License 
[Apache License 2.0](./LICENSE)