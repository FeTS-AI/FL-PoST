# Running Training

This guide assumes you finished preparing your dataset and reached [this step](https://docs.google.com/document/d/1731zXXb6ZRe6Nx5wnKBHZOdfEoTiTMAq/edit#heading=h.w0nnera5osyy). To start training, please follow the steps below.

**VERY IMPORTANT Note1: Steps 0, 1, 2, and 3 should be skipped in case you ran them successfully before.**

**VERY IMPORTANT Note2: If you face "invalid refresh token" error, reauthenticate by logging out first then logging in again.**

## 0. Change your MedPerf Branch and Re-install MedPerf

The new MedPerf code has been moved to a new branch. To update your MedPerf installation:

Go to the folder where you installed MedPerf (the `medperf` repository folder). Run the following (Don't forget to activate your medperf virtual environment):

```bash
git remote add training https://github.com/hasan7n/medperf.git
git fetch training
git checkout -b fl-poc training/fl-poc
pip install -e ./cli --force-reinstall
```

## 1. Mark your dataset as Operational

(This command may take some time) Run the following command to mark your dataset as Operational (i.e., ready for training):

```bash
medperf dataset set_operational -d DATASET_ID
```

Replace `DATASET_ID` with your dataset ID. This command will calculate the hash of your prepared dataset and some statistics. You will be presented with this information, and will be prompted to confirm uploading them to the MedPerf server.

To recall, you can get your dataset ID by running `medperf dataset ls --mine`.

![](images/op.png)

## 2. Associate your dataset with the training experiment

After marking your dataset as operational, run the following command so that your dataset is linked to the training experiment:

```bash
medperf dataset associate -t 1 -d DATASET_ID
```

Replace `DATASET_ID` with your dataset ID. You will be prompted to confirm.
![](images/assoc.png)

## 3. Get a certificate

To be identified by the aggregation server, you will need to get a certificate. Run the following command:

```bash
medperf certificate get_client_certificate -t 1
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

## 4. Start Training

#### 4.1 Set the GPU if you haven't already

If you want to use a GPU for training, follow the instructions found [in this section](https://docs.google.com/document/d/1731zXXb6ZRe6Nx5wnKBHZOdfEoTiTMAq/edit#heading=h.mru6t77kef2) if you haven't done so already.

#### 4.2 Start Training

Note that this command below should be left running for a long period of time. Make sure that you can keep your terminal open without interruptions, or use tools like tmux to run the command in a terminal window that you can detach.

Now run the following command to start training:

```bash
medperf dataset train -t 1 -d DATASET_ID --overwrite
```

Replace `DATASET_ID` with your dataset ID.

You should first see something similar to the screenshot below, where you are presented with the configuration set by the training experiment owner and will be used throughout training:

![](images/t1.png)

Confirm if you think everything looks good. Once you confirm, you will eventually reach a point where the training MLCube is downloaded successfully and your dataset is being preprocessed for training:

![](images/t2.png)

After some time, training will start. Please leave it running.
