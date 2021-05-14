# backdoor_federated_learning
This project reproduces some of the results of "How to Backdoor Federated Learning"(https://arxiv.org/abs/1807.00459) and supplements some parameter settings in the yaml file of the original project(https://github.com/ebagdasa/backdoor_federated_learning)
# Environment_setting
For the environment, follow the steps.txt. 

Win10, anaconda3, Intel i7-10700, GPU 2070super   
In this project, GPU is necessary. 

**Install and environment part**  

```python
conda create -n backdoor python=3.7  
conda activate backdoor  
conda install pytorch==1.0.0 torchvision==0.2.1 cuda100 -c pytorch  
pip install visdom  
pip install tqdm  
pip install PyYAML  
conda deactivate  
```



# Running
**Play:**

```python
conda activate backdoor  
python -m visdom.server # Keep this window on and create another window, then
conda activate backdoor 
cd backdoor_federated_learning-master
```

1.Run a no attack model:  

```python
python training.py
```

==training.py== load ==params.yaml== to run a no attack model of background wall. if you want to run for other kind of no attack model, change the poison_images_test and poison_images to target poison images. Changing epochs and save_on_epochs help to save model on different epochs.

2.Green Car Backdoor attack:  

```python
python train_green.py
```

3.Racing Stripe Car Backdoor attack:

```python
python train_stripe.py
```

4.Background wall Car Backdoor attack:  

```python
python train_wall.py
```

Run 2,3,4 for different kinds of semantic attack.
