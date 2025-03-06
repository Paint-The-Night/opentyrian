APP_NAME = OpenTyrian
APP_BUNDLE = $(APP_NAME).app
APP_CONTENTS = $(APP_BUNDLE)/Contents
APP_MACOS = $(APP_CONTENTS)/MacOS
APP_RESOURCES = $(APP_CONTENTS)/Resources

all: $(APP_BUNDLE)

$(APP_BUNDLE): $(APP_MACOS)/$(APP_NAME) $(APP_RESOURCES)/Info.plist $(APP_RESOURCES)/AppIcon.icns
	mkdir -p $(APP_BUNDLE)
	mkdir -p $(APP_CONTENTS)
	mkdir -p $(APP_MACOS)
	mkdir -p $(APP_RESOURCES)
	cp $(APP_MACOS)/$(APP_NAME) $(APP_MACOS)/
	cp $(APP_RESOURCES)/Info.plist $(APP_RESOURCES)/
	cp $(APP_RESOURCES)/AppIcon.icns $(APP_RESOURCES)/

$(APP_MACOS)/$(APP_NAME):
	$(MAKE) -C .. opentyrian
	cp ../opentyrian $(APP_MACOS)/$(APP_NAME)

$(APP_RESOURCES)/Info.plist: Info.plist
	cp Info.plist $(APP_RESOURCES)/Info.plist

$(APP_RESOURCES)/AppIcon.icns: AppIcon.icns
	cp AppIcon.icns $(APP_RESOURCES)/AppIcon.icns

clean:
	rm -rf $(APP_BUNDLE)
