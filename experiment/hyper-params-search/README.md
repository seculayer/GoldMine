# Hyper-Parameter Search

### Prerequisites

* python 3.5.x
* tensorflow_gpu (v. 2.0.0 b1)
* tensorflow_datasets(v. 3.1.0)
### Running
[Parameter Setting]
```json
{
  "dataset" : "mnist",
  "hpo_alg": "GA",
  "hpo_params" : {
    "mut_prob" : 0.5,
    "cx_prob" : 0.5,
    "sel_ratio" : 0.0,
    "mut_ratio" : 0.5,
    "cx_ratio" : 0.5,
    "n_steps" : 1,
    "n_params" : 3,
    "k_val" : 1,
    "eval_key" : "accuracy"
  },
  "ml_alg" : "DNN",
  "ml_params" : {
    "model_param":{
      "input_units" : "100",
      "output_units" : "1",
      "global_step" : "10",
      "early_type" : "2",
      "min_step" : "10",
      "early_key" : "accuracy",
      "early_value" : "0.98",
      "algorithm_type" : "classifier"
    },
    "pbounds":{
      "dropout_prob": [0, 0.5],
      "optimizer_fn": ["Adam", "rmsprop", "Adadelta"],
      "learning_rate": [0, 0.8],
      "act_fn": ["Tanh", "ReLU", "Sigmoid"],
      "hidden_units" : [3,1024]
    }
  }
}
```