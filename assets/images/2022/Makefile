# Images that need a copy at width 1024.
WIDE := \
  itineraires-et-horaires.jpg

# Images that need a copy at width 512.
NARROW := \
  10km.jpg \
  20km.jpg \
  45km.jpg \
  54km.jpg \
  70km.jpg \
  81km.jpg \

.PHONY: all
all: $(patsubst %.jpg,%-1024.jpg,$(WIDE)) $(patsubst %.jpg,%-512.jpg,$(NARROW))

%-512.jpg: %.jpg
	convert $< -resize 512 $@

%-1024.jpg: %.jpg
	convert $< -resize 1024 $@
