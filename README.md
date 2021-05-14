# metapoison anonymous submission


# Installation instructions

Install all packages as listed in ```environment.yml```, for example via anaconda.

# Running instructions:
* If you have a comet account, fill in your information in the ```.comet.config file```.

* Use ```train.py``` to generate weight samples and upload them to your comet API.

* Call ```main.py``` with your options (various options are defined in the argparser) to craft poisons.

* Run ```victim.py``` to validate the crafted poisons on a new network trained from scratch.

Since the comet_ml API has been updated, some API enpoints do not work anymore. Some changes has been made as follows
1. We hardcoded the number of the GPU to 1 since the set_available_gpus(utils.py) results in an error. 
2. We suggested to put your comet API key directly into the code, you will see "your_api_key" where you need to provide the API key
3. In main.py, comet_pull_weights_gen(api) has been updated for the new API 
4. In victim.py, comet_pull_next_poison() has been updated for the new API
5. there are some other changes regarding the training the model inside victim.py(e.g. patience)
