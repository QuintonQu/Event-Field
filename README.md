# Event-Field
 
## For the Galvanometer
This E2VID version is modified to use Apple mps (metal performace shader) to accelerate the GPU computation. 
please run rpg_e2vid with following command:
```
python run_reconstruction.py \                                                                                                                                                                                                                                 
  -c pretrained/E2VID_lightweight.pth.tar \
  -i ../example_data/galvanometer/250hz_fan_short.txt \
  --auto_hdr \
  --use_gpu \
--output_folder result/vh_galvo \
-T 1.0 \
--fixed_duration \
--show_events
```

Then stitch all the pictures into videos, then run "refocus/galvanometer_refocus.ipynb" to get the final result.

## For the Kaleidoscope
We also provide kaleidoscope data for timelens.
Please follow the Timelens instruction to run the timelens using below command:
```
python -m timelens.run_timelens ./checkpoint.bin $EVENTS_INPUT_DIR $FRAME_INPUT_DIR $FRAME_OUTPUT_DIR 0 $inserts
```
,where $EVENTS_INPUT_DIR is 'example_data/kaleidoscope/events', $FRAME_INPUT_DIR is 'example_data/kaleidoscope/images', $FRAME_OUTPUT_DIR is 'result/', $inserts is 7 in our case.                          

Then stitch all the pictures into videos, then run "refocus/kaleidoscope_refocus.ipynb" to get the final result.


