# EVMDIS MacOS Service Integration

It wraps [EVMDIS](https://github.com/Arachnid/evmdis) created by [Nick Johnson](https://github.com/Arachnid/) in a MacOS service, so it's readily accessible across the OS.


<img src="https://github.com/evertonfraga/evmdis-macos-service/raw/master/images/evmdis-service-medium.gif">


### Installation

#### 1. Download EVMDIS

_Copied from [EVMDIS - Building](https://github.com/Arachnid/evmdis#building)_

Retrieve the evmdis source. For example:

    go get github.com/Arachnid/evmdis

Build and install evmdis to $GOPATH/bin:

    go install github.com/Arachnid/evmdis/evmdis

Sanity check, assuming $GOPATH/bin is in your $PATH:

    evmdis -h

#### 2. Automator file

Place the `EVM Disassembler` file inside `~/Library/Services/`.

Open it with Automator, look for the "Run Shell Script" block and change the EVMDIS path to the full path of `evmdis` binary.

<img src="https://github.com/evertonfraga/evmdis-macos-service/raw/master/images/evmdis-path-change.png">

Save it and close Automator.
 

### How to trigger it?

I recommended having a global shortcut for it. Needless to say, beware of conflicts. This is how you should set it up:

<img src="https://github.com/evertonfraga/evmdis-macos-service/raw/master/images/evmdis-setting-global-keystroke.gif">

It should be available for apps that preserve the list of services in their context menu:

<img src="https://github.com/evertonfraga/evmdis-macos-service/raw/master/images/evmdis-context-menu.png">

Other option is under each app's Service submenu:

<img src="https://github.com/evertonfraga/evmdis-macos-service/raw/master/images/evmdis-services-menu.png">


### Example data

https://github.com/ethereum/tests/blob/develop/GeneralStateTests/stRevertTest/RevertPrecompiledTouch.json#L118
