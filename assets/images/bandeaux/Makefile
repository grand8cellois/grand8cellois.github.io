# The .webp images form the frames of the animation.
FRAMES := G8C.webp
# Delay, in milliseconds.
DELAY  := 5000
# The poster.
POSTER := ../2023/affiche.png

animation.webp: $(FRAMES)
	webpmux $(patsubst %.webp,-frame %.webp +$(DELAY),$(FRAMES)) -o $@

# Convert .png to .webp.
%.webp: %.png
	cwebp $< -o $@

# Convert .jpg to .png.
%.png: %.jpg
	magick convert $< $@

# The source image is Marly.
# A caption is superimposed in the lower left corner.
# The poster is superimposed in the lower right corner.
G8C.png: Marly.png Makefile
	magick convert $< \
	  -font helvetica -fill white -pointsize 72 \
	  -gravity southwest -annotate +50+50 "Grand Huit Cellois\\n17 septembre 2023" \
	  "(" $(POSTER) -resize 210 ")" -gravity southeast -geometry +50+50 -composite \
	  $@

.PHONY: clean
clean:
	git clean -fX .
