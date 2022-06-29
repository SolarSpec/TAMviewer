<div id="top"></div>

<!-- PROJECT SHIELDS -->
[![Contributors][contributors-shield]][contributors-url]
[![Forks][forks-shield]][forks-url]
[![Stargazers][stars-shield]][stars-url]
[![Issues][issues-shield]][issues-url]
[![MIT License][license-shield]][license-url]
[![LinkedIn][linkedin-shield]][linkedin-url]



<!-- PROJECT LOGO -->
<br />
<div align="center">
  <a href="https://github.com/SolarSpec/TAMviewer">
    <img src="images/logo.png" alt="SolarSpec" width="160" height="120">
  </a>

<h3 align="center">TAMviewer</h3>

  <p align="center">
    Repository to hold the importing and processing of TAM data
    <br />
    <a href="https://github.com/SolarSpec/TAMviewer"><strong>Explore the docs »</strong></a>
    <br />
    <br />
    <a href="https://github.com/SolarSpec/TAMviewer">View Demo</a>
    ·
    <a href="https://github.com/SolarSpec/TAMviewer/issues">Report Bug</a>
    ·
    <a href="https://github.com/SolarSpec/TAMviewer/issues">Request Feature</a>
  </p>
</div>



<!-- TABLE OF CONTENTS -->
<details>
  <summary>Table of Contents</summary>
  <ol>
    <li>
      <a href="#about-the-project">About The Project</a>
      <ul>
        <li><a href="#built-with">Built With</a></li>
      </ul>
    </li>
    <li>
      <a href="#getting-started">Getting Started</a>
      <ul>
        <li><a href="#prerequisites">Prerequisites</a></li>
        <li><a href="#installation">Installation</a></li>
      </ul>
    </li>
    <li><a href="#usage">Usage</a></li>
    <li><a href="#roadmap">Roadmap</a></li>
    <li><a href="#contributing">Contributing</a></li>
    <li><a href="#license">License</a></li>
    <li><a href="#contact">Contact</a></li>
    <li><a href="#acknowledgments">Acknowledgments</a></li>
  </ol>
</details>



<!-- ABOUT THE PROJECT -->
## About The Project

[![TAMviewer Screenshot][product-screenshot]](https://solarspec.ok.ubc.ca/)
Importing and processing of TAM data

<p align="right">(<a href="#top">back to top</a>)</p>



### Built With

* [MATLAB](https://www.mathworks.com/products/matlab.html)

<p align="right">(<a href="#top">back to top</a>)</p>



<!-- GETTING STARTED -->
## Getting Started

To begin using this app is very simple. Just verify you have the necessary prequisites and follow the installation instructions.

### Prerequisites

Make sure MATLAB is installed. It is available for download in the Software Distribution section under the Help tab after you log into Canvas. [https://canvas.ubc.ca/](https://canvas.ubc.ca/)

### Installation

1. Clone the repo to your PC
   ```sh
   git clone https://github.com/SolarSpec/TAMviewer.git
   ```
2. Browse repository
   ```
   View the relevant files
   ```

<p align="right">(<a href="#top">back to top</a>)</p>



<!-- USAGE EXAMPLES -->
## Usage
To begin, the user must load some arbitrary TAM data from a selected folder by pressing the "Load Data" button. _Please note that the total number of files in the folder must be a square number (e.g. 2^2 = 4 files, 3^2 = 9 files, 4^2 = 16 files, etc.) to ensure the image created is a square._ A UI prompt will appear that asks the user to direct the GUI to the desired TAM data, while iterating through multiple magnitudes to find the correct step size. This process is used to adjust the pixel coordinates to create a square image and separate the data properly. _If a certain channel is selected for the first .tdms file and is not present in the others, then the script follows a specified heirarchy of channels to assign: ["final A-B";"A-Test  dOD"] for processed data and ["B-Test  raw"; "A-Test  raw"] for raw data._ For ease of use, the correctly specified channel is applied to the KinPlot tab title when a pixel is selected, highlighted in green whereas a backup channel is highlighted in red.

After a channel is chosen, the app plots the average data and sets the T0 time. Next the app will generate the fit functions to create a pixel plot that relates to each unique file. Finally, three more useful interactive axes in the tab group at the bottom of the GUI are created for an in-depth analysis of the aggregated files. On the left panel, the user has the ability to switch between an "Intensity Derived" or "RGB" colour scheme. The former creates brighter colours corresponding to larger amplitudes whereas the latter uses colours that are similar in brightness but relates the T50% values (i.e. they are representative of the T50% values). The T0 time automatically sets to the highest peak as this is the shortest time where the data is not affected by the electronic rise time; however, the edit field on the left panel allows for manual selection as well as the interactability of the ROI line in the average plot itself. The colour scale time fields allow the user to manually input the times that determine the full colour range of the pixel plot. The shorter the range, the more distinct the colours. 

The user can select a specific pixel of the image plot that will update the KinPlot axes with the selected kinetics data. The HistPlot shows the distribution of the T50%'s for all pixels and its axes scale is determined by the colour scale values. The BkgrdPlot illustrates the DC background levels of each file, oriented in the same way as the pixel plot. The "Select Region" button allows the selection of multiple pixels/files in the image plot which will then reflect on the bottom kinetics tab as an averaged blue trace of the regions instead of the individual selected pixel coloured as a red trace. The user has the ability to add multiple regions or remove all of them and start over. Finally, the user can export certain variables to the workspace for easy investigation which include, the x and y data of all the files, pixel coordinates, the T50 times and the fit coefficients. The "Export Data" button will create a new directory called "ExportedData" which includes an image plot .jpg file and .mat files of the image data, ROI region points, pixel, histogram and T50 data.

This app is currently lacking in any examples. Coming soon!

_For more information on any of the internal functions, please refer to the [MATLAB Documentation](https://www.mathworks.com/help/matlab/)_

<p align="right">(<a href="#top">back to top</a>)</p>



<!-- ROADMAP -->
## Roadmap

See the [open issues](https://github.com/SolarSpec/TAMviewer/issues) for a full list of proposed features (and known issues).

<p align="right">(<a href="#top">back to top</a>)</p>



<!-- CONTRIBUTING -->
## Contributing

Contributions are what make the open source community such an amazing place to learn, inspire, and create. Any contributions you make are **greatly appreciated**.

If you have a suggestion that would make this better, please fork the repo and create a pull request. You can also simply open an issue with the tag "enhancement".
Don't forget to give the project a star! Thanks again!

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

<p align="right">(<a href="#top">back to top</a>)</p>



<!-- LICENSE -->
## License

Distributed under the BSD 3-Clause License. See `LICENSE.txt` for more information.

<p align="right">(<a href="#top">back to top</a>)</p>



<!-- CONTACT -->
## Contact

SolarSpec - [SolarSpec Website](https://solarspec.ok.ubc.ca/) - vidihari@student.ubc.ca

Project Link: [https://github.com/SolarSpec/TAMviewer](https://github.com/SolarSpec/TAMviewer)

<p align="right">(<a href="#top">back to top</a>)</p>



<!-- ACKNOWLEDGMENTS -->
## Acknowledgments

* [Group Leader - Dr. Robert Godin](https://solarspec.ok.ubc.ca/people/)
* [Group Alumni - James Kivai](https://solarspec.ok.ubc.ca/people/)
* [The Entire SolarSpec Team](https://solarspec.ok.ubc.ca/people/)

<p align="right">(<a href="#top">back to top</a>)</p>



<!-- MARKDOWN LINKS & IMAGES -->
<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->
[contributors-shield]: https://img.shields.io/github/contributors/SolarSpec/TAMviewer.svg?style=for-the-badge
[contributors-url]: https://github.com/SolarSpec/TAMviewer/graphs/contributors
[forks-shield]: https://img.shields.io/github/forks/SolarSpec/TAMviewer.svg?style=for-the-badge
[forks-url]: https://github.com/SolarSpec/TAMviewer/network/members
[stars-shield]: https://img.shields.io/github/stars/SolarSpec/TAMviewer.svg?style=for-the-badge
[stars-url]: https://github.com/SolarSpec/TAMviewer/stargazers
[issues-shield]: https://img.shields.io/github/issues/SolarSpec/TAMviewer.svg?style=for-the-badge
[issues-url]: https://github.com/SolarSpec/TAMviewer/issues
[license-shield]: https://img.shields.io/github/license/SolarSpec/TAMviewer.svg?style=for-the-badge
[license-url]: https://github.com/SolarSpec/TAMviewer/blob/main/LICENSE
[linkedin-shield]: https://img.shields.io/badge/-LinkedIn-black.svg?style=for-the-badge&logo=linkedin&colorB=555
[linkedin-url]: https://linkedin.com/in/haris-vidimlic-06730019b/
[product-screenshot]: images/Screenshot.png
