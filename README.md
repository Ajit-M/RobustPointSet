# RobustPointSet
A benchmark dataset to facilitate augmentation-independent robustness analysis of point cloud classification models. RobustPointSet comes with 6 different transformations: Noise, Translation, Missing part, Sparse, Rotation, and Occlusion.

<div align="center">
<img src="https://github.com/AutodeskAILab/RobustPointSet/blob/main/RobustPointSet.png" width="800" height="320">
</div>

--------------

### Evaluation Strategies

We test two different evaluation strategies on more than 10 models:

#### Strategy 1 (training-domain validation)
For this strategy, we train on `train_original.npy` without applying any data-augmentation, and test on each test set (i.e. `test_*.npy` ) separately.

#### Strategy 2 (leave-one-out validation)
For this strategy, each time we concatenate 6 train sets (i.e. the `train_*.npy` ones), and test on the test set (i.e. `test_*.npy` ) of the taken-out group. We repeat this process for all the groups. For example, we train with concatenation of `{train_original.npy, train_noise.npy, train_missing_part.npy, train_occlusion.npy, train_rotation.npy, train_sparse.npy}` and test on `test_translate.npy`. Similar to strategy 1, we don't apply any data-augmentation here. For both the strategies, the same label files can be used i.e. `labels_train.npy` and `labels_test.npy`.

-----------------

### Publication 

[RobustPointSet: A Dataset for Benchmarking Robustness of Point Cloud Classifiers]()

Citation info here

-----------------
### Download
The `.zip` file of the dataset can be accessed [here](https://github.com/AutodeskAILab/RobustPointSet/releases/tag/v1.0).

-----------------
### License

Please refer to the [dataset license](https://github.com/AutodeskAILab/RobustPointSet/blob/main/LICENSE.md).


