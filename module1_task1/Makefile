POST_TITLE := $(shell echo $$POST_TITLE)
POST_NAME := $(shell echo $$POST_NAME)

build:
    hugo --minify

clean:
    rm -rf dist/*

post:
    hugo new posts/$(POST_NAME).md
    sed -i '1s/^/---\n/' content/posts/$(POST_NAME).md
    sed -i '1s/$$/\n---/' content/posts/$(POST_NAME).md
    sed -i "s/title: .*/title: '$(POST_TITLE)'/g" content/posts/$(POST_NAME).md

.PHONY: build clean post
