help:
	@echo 学習する images640
	@echo " $$ make train_4c"
	@echo 学習する images640_bool
	@echo " $$ make train_2c"
	@echo 学習する full_data640
	@echo " $$ make train_full_2c"
	@echo 学習する full640_images640-bool
	@echo " $$ make train_full640_images640-bool"
	@echo 学習する train_images640_3c
	@echo " $$ make train_images640_3c"

	@echo 予測する full_data640
	@echo " $$ make predict_full_2c"
	
	@echo 予測データ、学習済みモデルを削除する
	@echo " $$ make rm"


# images640
train_4c:	
	python train.py --data ./fig_data/images640.yaml --cfg models/yolov5s.yaml --weights yolov5s.pt --batch-size 10 --epoch 300 --imgsz 640

# images640_bool
train_2c:
	python train.py --data ./fig_data/images640_bool.yaml --cfg models/yolov5s.yaml --weights yolov5s.pt --batch-size 10 --epoch 300 --imgsz 640

# full_data640
train_full_2c:	
	python train.py --data ./fig_data/full_data640.yaml --cfg models/yolov5s.yaml --weights yolov5s.pt --batch-size 10 --epoch 300 --imgsz 640

# full640_images640-bool
train_full640_images640-bool:
	python train.py --data ./fig_data/full640_images640-bool.yaml --cfg models/yolov5s.yaml --weights yolov5s.pt --batch-size 10 --epoch 300 --imgsz 640

# images640_3c
train_images640_3c:
	python train.py --data ./fig_data/images640_3c.yaml --cfg models/yolov5x.yaml --weights yolov5x.pt --batch-size 10 --epoch 300 --imgsz 640

# trialrun1_full_64_48
train_trialrun1_full_64_48:
	python train.py --data ./version3/trialrun1_full_64_48.yaml --cfg models/yolov5x.yaml --weights yolov5x.pt --batch-size 10 --epoch 300 --imgsz 640

# -------------------------------------------------------------------------------------------------------------------------------------------------------------------

# full_data640
predict_full_2c:
	python detect.py --data ./fig_data/full_data640.yaml --weight runs/train/exp_train_full_2c/weights/best.pt --source ./fig_data/images640/ --imgsz 640

# full640_images640-bool
predict_full640_images640-bool:
	python detect.py --data ./fig_data/full640_images640-bool.yaml --weight runs/train/exp_full640_images640-bool/weights/best.pt --source ./fig_data/images640/ --imgsz 640

# images640_3c
predict_images640_3c:
	python detect.py --data ./fig_data/images640_3c.yaml --weight runs/train/exp_images640_3c/weights/best.pt --source ./fig_data/fulldata_and_trialrun_640 --imgsz 640

# trialrun1_full_64_48
predict_trialrun1_full_64_48:
	python detect.py --data ./version3/trialrun1_full_64_48.yaml --weight runs/train/exp_trialrun1_full_64_48/weights/best.pt --source ./fig_data/fulldata_and_trialrun_640 --imgsz 640
	python detect.py --data ./version3/trialrun1_full_64_48.yaml --weight runs/train/exp_trialrun1_full_64_48/weights/best.pt --source ./fig_data/fulldata_and_trialrun_shaped_640 --imgsz 640
rm:
	rm -rf runs/*