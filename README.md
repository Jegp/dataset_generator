# Installation instructions

    # Clone experiment to your preferred location
      (do not clone into your nrpStorage directly)


	  cd /your_experiment_path
    git clone https://github.com/ncskth/dataset_generator.git
    cd dataset_generator

    # symlink experiment into nrpStorage
    ln -s /your_experiment_path/dataset_generator/NRPExp_DVSDatabaseGenerator $HOME/.opt/nrpStorage/NRPExp_DVSDatabaseGenerator

    # Copy Model files
    cp -r Models/* $HBP/Models

    # Copy ROS packages (contains Kuka IIWA MoveIt configuration)
    cp -r GazeboRosPkgs/src/* $HBP/GazeboRosPackages/src/

    # Link new models
    cd $HBP/Models
    ./create-symlinks.sh

    # Compile ROS Packages
    cd $HBP/GazeboRosPkgs
    catkin_make -j8
