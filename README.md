# NLP-Dependency-Parsing-Feedforward-Networks
I trained a dependency parsing model based on the “arc-standard” system.

# Part 1

To reimplement my model, you should first change ‘from network_3 import Network’ to ‘from network import Network’ in driver.py and depModel.py. Basically network.py is used for Part 1 and Part 2, and network_3.py is used for part 3.

(Before reimplemeting, make sure you have vocabs.word, vocabs.pos, vocabs.labels, vocabs.actions, train.data, dev.data in data directory)

To train the model, run python2 src/driver.py --model=./model/model_q1 --vocab=./data/vocabs_q1.data

To validate the model, change “input = ["--model", "./model/model_q3", "--vocab", "./data/vocabs_q3.data"]”(this is for part3) in depModel.py to “input = ["--model", "./model/model_q1", "--vocab", "./data/vocabs_q1.data"]” and run python2 src/depModel.py trees/dev.conll outputs/dev_part1.conll python2 src/eval.py trees/dev.conll outputs/dev_part1.conll

To test model, run python2 src/depModel.py trees/test.conll outputs/test_part1.conll

# Part 2

To reimplement my model, first change ‘from network_3 import Network’ to ‘from network import Network’ in driver.py and depModel as it is said in Part 1.

To train the model, run python2 src/driver.py --model=./model/model_q2 --vocab=./data/vocabs_q2.data -hidden1=400 --hidden2=400

To validate the model, change “input = ["--model", "./model/model_q3", "--vocab", "./data/vocabs_q3.data"]” in depModel.py to “input = ["--model", "./model/model_q2", "-vocab", "./data/vocabs_q2.data"]” and run python2 src/depModel.py trees/dev.conll outputs/dev_part2.conll python2 src/eval.py trees/dev.conll outputs/dev_part2.conll

To test model, run python2 src/depModel.py trees/test.conll outputs/test_part2.conll

# Part 3

To train the model, make sure you have ‘glove.6B.200d.txt’ on top and run python2 src/driver.py --model=./model/model_q3 --vocab=./data/vocabs_q3.data -hidden1=400 --hidden2=400 --we=200 --pre_trained="./glove.6B.200d.txt"

To validate the model, run python2 src/depModel.py trees/dev.conll outputs/dev_part3.conll python2 src/eval.py trees/dev.conll outputs/dev_part3.conll

To test model, run python2 src/depModel.py trees/test.conll outputs/test_part3.conll
