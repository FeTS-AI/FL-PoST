# Running Training

**Note: If you face "invalid refresh token" error, reauthenticate by logging out first then logging in again.**

# Important steps for the Final Model Training

For the final model training to happen smoothly without interruption, and to minimize your interaction with the software in the upcoming weeks, please do the following:

- Delete the MedPerf logs to avoid any unexpected disk space shortage issue, by running the following:

```bash
rm ~/.medperf_logs/*
```

- You should re-authenticate now if you haven't done so in the past month. To re-authenticate, logout then login again, as follows (and follow instructions printed on the screen when you run the login command):

```bash
medperf auth logout
medperf auth login
```

- Go to the folder where you installed MedPerf (the `medperf` repository folder) and run `git pull` to get the latest changes.
- For step number 2 below, make sure you use the `--restart_on_failure` flag. We may change training configuration during the upcoming to test different models. If you don't use the `--restart_on_failure` flag, you will have to manually restart the command when we change the configuration.

## 0. Install MedPerf if you lost your previous installation

This step is only if you want to install medperf again. If you still have your medperf installation from previous runs, **then skip this section, and activate your medperf virtual environment.**

Run the following to install MedPerf (Don't forget to create and/or activate your medperf virtual environment):

```bash
git clone https://github.com/hasan7n/medperf.git
cd medperf
git checkout -b fl-poc origin/fl-poc
pip install -e ./cli --force-reinstall
```

## 1. Get a certificate

**This step needs to be rerun if you haven't run it after 8th April 2025.**
To be identified by the aggregation server, you will need to get a certificate. Run the following command:

```bash
medperf certificate get_client_certificate -t 1 --overwrite
```

You will be presented with a link and a 12-letters code:

![](images/c1.png)

Copy the provided link `https://auth.medperf.org/activate` and paste it in your browser to open it. Then, copy the 12-letters code you have on your terminal (in the example screenshot above, it is `KLZK-ZNDD-GFQJ`). Paste this code in the form that you see when you opened the link, then click Continue. You will then see a page similar to the one below:

![](images/c3.png)

Double-check that this is the 12-letters code you copied and pasted. Then, click Confirm. The next steps are similar to the login flow that you have performed when you logged in to MedPerf. You will have to enter your email address and receive an 8-digits code in your inbox. At the end, you should see the following on your browser:
![](images/c7.png)

And you should see something similar to the screenshot below in your terminal:

![](images/c8.png)

After this, you are ready to start the training process.

## 2. Start Training

To recall, you can get your dataset ID by running `medperf dataset ls --mine`.

#### 4.1 Set the GPU if you haven't already

If you want to use a GPU for training, follow the instructions found [in this section](https://docs.google.com/document/d/1731zXXb6ZRe6Nx5wnKBHZOdfEoTiTMAq/edit#heading=h.mru6t77kef2).

#### 4.2 Start Training

You have the option to run training with `--restart_on_failure` flag, which means that the process will restart by itself if it encountered a failure, or if the experiment organizers change the training configuration. Note that this means the command will not wait for your approval on the training configuration, it will only ask you to confirm one time that you are OK with automatic restarts. **Don't use this flag if you didn't test with us before and successfully trained for at least one round,** otherwise you may not easily figure out that you have an error that needs our help.

Running the command in this section should be left running for a long period of time. Make sure that you can keep your terminal open without interruptions, or use tools like tmux to run the command in a terminal window that you can detach.

Now run the following command to start training: (Replace `DATASET_ID` with your dataset ID.)

```bash
medperf dataset train -t 1 -d DATASET_ID --restart_on_failure
```

If you want to skip the restart_on_failure confirmation prompt, use the following flag additionally `--skip_restart_on_failure_prompt`:

```bash
medperf dataset train -t 1 -d DATASET_ID --restart_on_failure --skip_restart_on_failure_prompt
```

If you don't want to use `--restart_on_failure`, run this:

```bash
medperf dataset train -t 1 -d DATASET_ID --overwrite
```

If you didn't use `--restart_on_failure`, you should first see something similar to the screenshot below, where you are presented with the configuration set by the training experiment owner and will be used throughout training:

![](images/t1.png)

Confirm if you think everything looks good. Once you confirm, you will eventually reach a point where the training MLCube is downloaded successfully and your dataset is being preprocessed for training:

![](images/t2.png)

After some time, training will start. Please leave it running.
