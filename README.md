<h1 align="left">Adding/Extending Storage Red Hat</h1>

###

<p align="left">My name is Fidelis and I'm a Software Developer/Cloud Engineer.</p>

###

<h2 align="left">About me</h2>

###

<p align="left">✨ Documenating My Journey<br>📚 I'm currently learning ...<br>🎯 Goals: ...<br>🎲 Fun fact: ...</p>

###

<h2 align="left">Increasing Storage on my RHEL</h2>

###

<p align="left">Initial Storage Screenshot</p>

###

<div align="center">
  <img height="200" src="https://res.cloudinary.com/dv6f4g4l0/image/upload/v1757953626/firststorage_mmcffh.png"  />
</div>

###

<h2 align="left">Step 1: Check your disks</h2>

###

<p align="left">Run:<br>✨ lsblk<br><br>Then confirm if the newly added storage is present</p>

###

<h2 align="left">Step 2: Create a New Partition</h2>

###

<p align="left">Run:<br>✨ sudo fdisk /dev/sdc<br><br>Note That the SDC can also be SDD or SDE depending on the amout of disk you have added <br><br>Run this to create a new Partition <br><br>Inside fdisk:<br>Press n (new partition)<br>Press p (primary)<br>Accept defaults by pressing Enter Key (to use full disk) <br>Press w (write and exit)</p>

###

<h2 align="left">Step 3 Merging Partitions</h2>

###

<p align="left">Run: <br><br>✨ partprobe /dev/sda4<br><br>Check the correct/new partition name and replace "sda4" with that example, use sda5 or sda3 instead if it is the latest partition  <br><br>Run:<br>✨ pvcreate /dev/sda1 /dev/sda4<br>or<br>✨ pvcreate /dev/sda3 /dev/sda4<br><br>Depending on the partition name, this will extend the storage to the newly created partition <br><br>Run <br>✨ lvextend -L 500G /dev/mapper/rhel-home<br><br>✨ lvextend -L 500G /dev/mapper/rhel-home<br>These commands ensure that the folder directory is using 100% of the storage that was added.<br><br><br>✨ xfs_growfs /home<br><br>✨ df -h /home<br><br>Run:<br>✨ lsblk</p>

###

<p align="left">Final Storage Screenshot</p>

###

<div align="center">
  <img height="200" src="https://res.cloudinary.com/dv6f4g4l0/image/upload/v1757953626/finalstorage_eh29v9.png"  />
</div>

###

<div align="left">
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/redhat/redhat-original.svg" height="40" alt="redhat logo"  />
  <img width="12" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/bash/bash-original.svg" height="40" alt="bash logo"  />
  <img width="12" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/docker/docker-original.svg" height="40" alt="docker logo"  />
</div>

###
