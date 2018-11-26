# Time Delays

Time Delays is a video installation offering an altered mirror of space and time. It has been developed by [Robin Lamarche-Perrin](https://www-complexnetworks.lip6.fr/~lamarche/) and [Bruno Pace](https://de.linkedin.com/in/bruno-pace) for [In the Dark](http://www.movingcells.org), a contemporary art exhibition which took place in Leipzig during the month of October 2015.

Here is an example of use of this installation with the [Compagnie 121](http://cie121.com/) at [EP7](https://ep7.paris/) in April 2018:
https://www.facebook.com/robin.homepage/videos/10155330632946720/

### Installation

* Install OpenCV:
```
sudo apt-get install libopencv-dev
```

* Clone the project:
```
git clone https://github.com/Lamarche-Perrin/time-delays
```

* Compile the files:
```
cd time-delays
g++ -Wall -O3 -pthread time-delays.cpp -o time-delays `pkg-config --cflags --libs opencv`
```

* Run the program:
```
./time-delays <input>
```
where `<input>` is an optional parameter that is either
* the camera id you want to stream from (list devices with `v4l2-ctl --list-devices` once `v4l-utils` is installed)
* or the path to a video file you want to stream from.

If not specified, the application will try to open the webcam with id `0`.


### Control

* `<Space>` to switch black screen on (or off)
* `<Escape>` to close the application
<br><br/>

* `0` to suppress delay
* from `1` to `9` to set delay (from 15 frames to 135 frames, that is from 0.5 to 4.5 seconds in the case of 30fps)
* `+` to increase delay by 1
* `-` to decrease delay by 1
<br/><br/>

* `<Enter>` to switch heterogeneous delay on (or off)
* `h` to switch to horizontal delay
* `v` to switch to vertical delay
* `r` to reverse the direction of delay
* `s` to activate or deactivate symmetric delay


### License

Copyright © 2015-2018 Robin Lamarche-Perrin and Bruno Pace  
Contact: <Robin.Lamarche-Perrin@lip6.fr>

This program is free software: you can redistribute it and/or modify it under the terms of the GNU General Public License as published by the Free Software Foundation, either version 3 of the License, or (at your option) any later version.

This program is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the GNU General Public License for more details.

You should have received a copy of the GNU General Public License along with this program. If not, see <http://www.gnu.org/licenses/>.
