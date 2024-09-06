# LMM_RAG_Workshop_GPU

# Before start: <br />
make sure you have 
1. models folder if not get it from here:https://drive.google.com/drive/folders/11BEK-gFWjFB1Qb3mxHMg1OCYQn-QtV29?usp=drive_link<br />
/models<br />
   > /Layout<br />
   > /MFD<br />
   > /MFR<br />
   > README.MD<br />

2. text parquet file if not get it from here: https://drive.google.com/file/d/1DwXRLUqc7W4fLAtZR3XWiLva0Dc2VBAY/view?usp=sharing<br />

conda environment that used for this part is: LMMRAGwithGPU from computer 391<br />
.env for test can use .env_for_testing<br />


# Part1 Database Preparation
including: <br />
- image extrcation <br />
- captiongeneration <br />
- text OCR <br />

these 3 using same environment basically start from  1 -> 2 -> 3 <br />
1. imageextract.ipynb -> will give you crop image folder and full page folder, and also give you .json pairing each image to page number <br />
2. captiongeneration.ipynb -> will give you .json of image and associate caption <br />
3. textOCR.ipynb -> will give you .json of Text OCR <br />

So after these 3 steps you will get <br />
1. imagecaption.json <br />
2. text.json <br />


# Part2 Embedding and Searching

including:  <br />
- embed.ipynb <br />

You may reuse the conda env from part 1. <br />
## Pipeline <br />
1. After Part1 you get .json for image and .json for text dataset
2. **parquet files:** Run `embed.ipynb` to read from the above 2 json files and embed both, stored to `xxx_text.parquet` and `xxx_image.parquet` <br />
3. **RAG:** Run `rag.ipynb` to perform vector search and get RAG results. <br />



# Part3 Generation

run rag.ipynb
