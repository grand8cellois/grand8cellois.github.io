# We assume that every .jpg file is a source image.
# We show the most recent images first.
IMAGES := $(shell ls *.jpg | sort -r)
# The .webp images form the frames of the animation.
FRAMES := $(patsubst %.jpg,%.webp,$(IMAGES))
# Delay, in milliseconds.
DELAY  := 5000

animation.webp: $(FRAMES)
	webpmux $(patsubst %.webp,-frame %.webp +$(DELAY),$(FRAMES)) -o $@

# Convert .jpg to .webp.
%.webp: %.jpg
	cwebp $< -o $@

.PHONY: clean
clean:
	git clean -fX .
