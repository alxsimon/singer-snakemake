environment.squashfs: channels.scm manifest.scm
	guix time-machine -C $< -- \
	pack -f squashfs -m $(word 2, $^) \
	-S /bin=bin --entry-point=/bin/bash \
	| xargs -I % sh -c 'cp % $@ && chmod 664 $@'

clean:
	rm -f environment.squashfs
