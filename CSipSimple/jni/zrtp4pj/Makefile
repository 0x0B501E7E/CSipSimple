# This makefile aim is only for now to address source checkout and patch
zrtpcpp_repo := git://github.com/r3gis3r/ZRTPCPP.git
zrtpcpp_tag := V3.2.0


git_update=git fetch --tags; \
git checkout origin; \
git checkout $(1);

all :
	# For now we do nothing to build - it's made by android_toolchain
	
init : sources
	# Init done

sources :
	cd sources/zsrtp; \
	git clone $(zrtpcpp_repo) zrtp; \
	cd zrtp; \
	$(call git_update, $(zrtpcpp_tag))

update : sources
	@cd sources/zsrtp/zrtp; \
	if grep -q "wernerd" .git/config; then git remote set-url origin $(zrtpcpp_repo); fi; \
	$(call git_update, $(zrtpcpp_tag))
