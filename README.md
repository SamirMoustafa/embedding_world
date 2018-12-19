
OpenAI gym Embedding world Demo
===============================

<div align="center">
  <img width="40%" src="https://raw.githubusercontent.com/SamirMoustafa/gym-embedding-world/master/assets/9-dimensional-hypercube.gif"><br><br>
  <h6>An eight-dimensional hypercube graph.</h6>
</div>

[![Build Status](https://travis-ci.org/SamirMoustafa/gym-embedding-world.svg?branch=master)](https://travis-ci.org/SamirMoustafa/gym-embedding-world)

Implementation of N-dimension world environments for word embedding compatible with [OpenAI gym](https://github.com/openai/gym>).

Requirements:
- Python 3.5+
- OpenAI Gym
- NumPy
- Gensim

Install environment on anaconda
-------------------------------

    $ conda env create -f gym-embedding-world/environment.yml
    $ source embedding-world
    $ pip install -e gym-embedding-world/.

Install environment on colab
----------------------------

    !git clone "https://github.com/SamirMoustafa/gym-embedding-world.git"
    !pip install -e gym-embedding-world/.
    !mv gym-embedding-world gym-embedding-world-org
    !cp -r gym-embedding-world-org/embedding_world /content
    !ls embedding_world

Usage
-----

        $ python >>> import gym
        $ python >>> import embedding_world
        $ python >>> env = gym.make('embedding_world-v0')
        $ python >>> env.handle_goals("this is phrase example")
        $ python >>> state, reward, done, info = env.step('dim(0)+1')

``embedding_world-v0``
----------------------

Embedding world is simple N-dimension world for example the [Stanfrod GloVe](https://nlp.stanford.edu/projects/glove/) or [facebook fastText models](https://github.com/facebookresearch/fastText/blob/master/pretrained-vectors.md).

There are `2N` actions `{dimension(i)+1, dimension(i)-1}` ∀ i in range from 1 to N


which deterministically cause the corresponding state transitions
but actions that would take an agent of the grid leave a state unchanged.
The reward is -1 for all tranistion until the goal is reached.
The terminal state(goal) is represent in a vector/s.

Please use this bibtex if you want to cite this repository in your publications:

```
@misc{embedding_world,
    author = {Samir Moustafa},
    title = {Embedding Environment for OpenAI Gym},
    year = {2019},
    publisher = {GitHub},
    journal = {GitHub repository},
    howpublished = {\url{https://github.com/SamirMoustafa/gym-embedding-world}}
}
```
This environment has been built as part of graduation project at [University of Alexandria, Department of Computer Science](http://sci.alexu.edu.eg/index.php/en/)

