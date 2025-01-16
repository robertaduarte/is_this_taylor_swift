#Starting by finding pictures by installing icrawler 
!pip install icrawler

import os
from icrawler.builtin import GoogleImageCrawler
from PIL import Image

#finding pictures 
google_crawler = GoogleImageCrawler(storage={'root_dir': 'path'}, parser_threads=1)
google_crawler.crawl(keyword='taylor swift', max_num=1000, file_idx_offset=0)

#treating the pictures
#be careful because this is not data augmentation yet
#I'll add the data augmentation soon

def resize_image(input_path, output_path, size):

    for file_name in os.listdir(input_path):

      try:
          with Image.open(input_path+file_name) as img:

              img = img.convert("RGB")
              resized_img = img.resize(size)
              resized_img.save(output_path+file_name)
        
          print(f"Image saved to {output_path}, resized to {size}.")

      except Exception as e:
          print(f"Error processing {input_path}: {e}")


input_file = 'path to images'
output_file = 'path to save resized images'
size = (256, 256) #256 x 256 is really small and probably the CNN will not work well but we'll see

resize_image(input_file, output_file, size)
