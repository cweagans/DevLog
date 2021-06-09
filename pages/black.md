---
title: black
tags: tools
---

- [Calm Code](https://calmcode.io/black/introduction.html)
- `.pre-commit-config.yaml`
	-
	  ```yml
	  repos:
	    - repo: https://github.com/psf/black
	      rev: stable
	      hooks:
	        - id: black
	          language_version: python3.6
	  ```
	- This will run Black before every commit