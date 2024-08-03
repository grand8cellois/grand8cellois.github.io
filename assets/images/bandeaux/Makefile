# We assume that every .jpg file is a source image.
# We show the most recent images first.
IMAGES := $(shell ls *.jpg | sort -r)
# The processed .webp images form the frames of the animation.
FRAMES := $(patsubst %.jpg,%-processed.webp,$(IMAGES))
# Delay, in milliseconds.
DELAY  := 5000

animation.webp: $(FRAMES)
	webpmux $(patsubst %.webp,-frame %.webp +$(DELAY),$(FRAMES)) -o $@

# Convert .jpg to .png.
%.png: %.jpg
	magick convert $< $@

# The poster.
POSTER := ../2024/affiche.png

# Each source image is processed as follows.
# A caption is superimposed in the lower left corner.
# The poster is superimposed in the lower right corner.
%-processed.png: %.png Makefile
	magick convert $< \
	  -font helvetica -fill white -pointsize 72 \
	  -gravity southwest -annotate +50+50 "Grand Huit Cellois\\n6 octobre 2024" \
	  "(" $(POSTER) -resize 210 ")" -gravity southeast -geometry +50+50 -composite \
	  $@

# Convert .png to .webp.
# -q is the quality factor.
%.webp: %.png
	cwebp -q 40 $< -o $@

.PHONY: clean
clean:
	git clean -fX .
