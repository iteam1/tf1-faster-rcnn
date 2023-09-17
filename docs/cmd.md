- install required packages: 

        pip install labelme && \
        pip install contextlib2 && \
        pip install IPython && \
        pip install pandas && \
        apt-get update && apt-get install ffmpeg libsm6 libxext6  -y && \
        apt-get update && apt-get install libgl1 && \
        apt-get install -y libgl1-mesa-dev && \
        apt-get install -y libglib2.0-0 &&

- Create train data: `python scripts/xml_to_csv.py -i dataset/train -o dataset/train_labels.csv`

- Create train data: `python scripts/xml_to_csv.py -i dataset/val -o dataset/val_labels.csv`

- Create train data:

        python scripts/generate_tfrecord.py --csv_input=dataset/train_labels.csv \
        --output_path=dataset/train.record \
        --image_dir=dataset/train_img
