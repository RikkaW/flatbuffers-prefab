# FlatBuffers Prefab

Prefab package for FlatBuffers (https://github.com/google/flatbuffers).

## Integration

This is a [Prefab](https://google.github.io/prefab/) library, so you will need to enable it in your project (requires Android Gradle Plugin 4.1+):

gradle.properties:

```properties
# Header only package is not supported by the default version of prefab
# https://github.com/google/prefab/issues/122
android.prefabVersion=1.1.2
```

```gradle
android {
    ...
    buildFeatures {
        ...
        prefab true
    }
}
```

Add dependency:

```gradle
repositories {
    mavenCentral()
}

dependencies {
    implementation 'dev.rikka.ndk.thirdparty:flatbuffers:1.12.0'
}
```

## Usage

### ndk-build

```makefile
LOCAL_STATIC_LIBRARIES := flatbuffers

# You can remove this block if you are using NDK r21+.
ifneq ($(call ndk-major-at-least,21),true)
    $(call import-add-path,$(NDK_GRADLE_INJECTED_IMPORT_PATH))
endif

$(call import-module,prefab/flatbuffers)
```

### CMake

```cmake
find_package(flatbuffers REQUIRED CONFIG)
target_link_libraries(<your lib> flatbuffers::flatbuffers)
```