# My blog

This is a random collection of various projects.
The blog template was forked from Karpathy's personal blog, visible here https://github.com/karpathy/karpathy.github.io

The contents of this website (pages, photos and writing) are my original work and no ai text or images are used.

Compress images in batches for upload:
for i in *; do convert $i -resize 1920x $i; done;