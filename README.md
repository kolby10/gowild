#  GoWild Search

# GoWild Flight Scraper Destination Finder

This program allows users with Frontier Airlines' GoWild all-you-can-fly pass to quickly check the availability of flights to all different destinations. By scraping Frontier Airlines' website, the program provides information on flights available for the current day or the next day from the specified origin airport.
This program is designed for those with the GoWild pass who embrace the spontinaity of it and want to see all available adventures they can take within the 24-hour booking period. 

### Updates
Most recent update allows for roundtrips! It will automatically search for next-day return flights for today departures.
Also should run faster by checking dates first and improved use for rate limiting.

## Prerequisites
Before running `gowild_scraper.py`, make sure you have the following installed on your system:

- `Python 3.x`
If you don't have Python installed, follow the instructions [here](#downloading-python) to download it.
- `requests` library
- `beautifulsoup4` library
- `browsercookie` library

You can install the required libraries using `pip`:

```
pip install requests beautifulsoup4 browsercookie
```
If you are confused by this jump to [my broken down guide :)](#easy-guide) for set up.

## Usage

To run the program, execute the following command in your terminal [what's my terminal?](#opening-your-terminal):

```
python flight_availability_checker.py -o [origin] -d [dates] -c -r [resume]
```

The program accepts the following command-line arguments:

- `-o` or `--origin`: Specifies the origin airport IATA code.
- `-d` or `--dates`: Specifies the dates to show flights for. Use the following values:
  - `1`: Today
  - `2`: Tomorrow
  - `3`: Both today and tomorrow
- `-c` or `--cjs`: (Optional) Use browser cookies. If specified, the program will use cookies from your default web browser.
- `-r` or `--resume`: (Optional) Index of the airport to resume from. Use index `21` to only search for contiguous US destinations.

Note: The `-c` and `-r` options are optional, and you can omit them if not needed.

### Example input

To check the flight availability from the origin airport "PHX" (Phoenix) for both today and tomorrow, run the following command:

```
python gowild_scraper.py -o PHX -d 3
```

This will display the available flights for both today and tomorrow from Phoenix.

The program will display the available flights and their details, including departure dates, total flight time, and prices. If there are roundtrip flights available for the next day, they will be marked with `**`. 

*New!* Next day return flights are only searched for if you plan on departing today. Do you want something different? Let me know!

After displaying the flight information, the program will list the available destinations

and ask for your input again. You can enter the index number of a destination to check for flights from your origin to that destination. Alternatively, you can enter `exit` to quit the program.

## Limitations

- Frontier Airlines' website may have usage restrictions or rate limiting in place. Running the program too frequently or making too many requests in a short period could lead to IP blocking or other issues. It is recommended to use the program responsibly and respect the website's [terms of service](https://www.flyfrontier.com/legal/terms-of-use/?mobile=true).

## License

This project is licensed under the [MIT License](https://opensource.org/licenses/MIT).

## Disclaimer

This program is for educational purposes only. Use it responsibly and respect the website's terms of service found [here](https://www.flyfrontier.com/legal/terms-of-use/?mobile=true). The developers are not responsible for any misuse or consequences caused by using this program.

If you encounter any issues or have suggestions for improvements, please feel free to contribute or open an issue in the project repository.

I would love further contributions from fellow lovers of travel and innovation. 

This program was mainly an educational personal project for myself.

That being said there are many imperfections and areas of improvement to make this program more efficient and user friendly. 

I'm making this repo public so I can learn more from other possible contributors. 

### Happy flying!!!
 
If any of you would like to help further this educational project for the community but don't code, I've created a [**form**](https://forms.gle/B7Xd76NiZLTtxL9A9) where you can leave feedback for update inspo!

### Example output

```
CUN to BNA: Nashville available:
flight 1. 1 Stop MCO
        Date: 07-06
        Depart: 10:01 AM
        Total flight time: 23 hrs 53 min
Price: $100.18
CUN to BNA: 1 GoWild flights available for Thursday, 07-06-23

**Return flight available:
flight 1. 1 Stop MCO
        Date: 07-07
        Depart: 10:49 AM
        Total flight time: 22 hrs 31 min
Price: $84.74
flight 2. 1 Stop PHL
        Date: 07-07
        Depart: 2:45 PM
        Total flight time: 20 hrs 22 min
Price: $84.74
BNA to CUN: 2 GoWild return flights available for Friday, 07-07-23
No flights from CUN to AUS

45 destinations found from CUN:
**NAS: Bahamas
**BQN: Aguadilla, Puerto Rico
**SJU: San Juan, Puerto Rico
**PHX: Phoenix
**XNA: Arkansas
**LIT: Little Rock, AR
**ONT: Ontario
**SAN: San Diego
....
** = next day return flight available
```

## Easy Guide

- [Downloading Python](#downloading-python)
- [Downloading additional libraries](#downloading-libraries)
   - [Opening your terminal](#opening-your-terminal)
- [Downloading the flight search program](#downloading-this-program)
- [Running the flight search program](#running-the-flight-search-program)
- [Example output](#example-output)

### Downloading Python
- **macOS**
1. Open a web browser and go to the official Python website: [https://www.python.org/downloads/macos/](https://www.python.org/downloads/macos/).
2. Download the latest version for macOS.
3. Once the installer is downloaded, open it and follow the instructions to install Python.
4. Jump back [here](#downloading-libraries) to continue setting up the program

- **Windows**
1. Open a web browser and go to the official Python website: [https://www.python.org/downloads/windows/](https://www.python.org/downloads/windows/).
2. Download the latest version for Windows
4. Once the installer is downloaded, open it and follow the instructions to install Python.
5. Jump back [here](#downloading-libraries) to continue setting up the program

- **Linux**
   - Python is usually pre-installed on most Linux distributions. Open the terminal and type `python3 --version` to check if it's already installed. If not, use your package manager to install Python (e.g., `sudo apt install python3` for Ubuntu-based distributions).

### Downloading Libraries

Next step is downloading the additional python libraries, like extension packs, that I have utilized in the program. If you have installed and set up Python correctly, you should be able to download the packages through your terminal.
Instructions for opening your terminal for [Windows](#windows), [Mac](#macos), [Linux](#linux)

With your terminal/compand prompt open you can use the *pip* installer that comes with python.
*copy, paste, enter, and it should start doing its computer things beep boop*
```
pip install requests beautifulsoup4 browsercookie
```

### Opening your terminal

#### Windows 
   Press `Win + R` to open the Run dialog, type `cmd`, and press Enter.

#### macOS
   Press `Command + Space` to open Spotlight Search, type `Terminal`, and press Enter.

#### Linux
   Press `Ctrl + Alt + T` to open the terminal.

### Downloading this program

Alright we're almost there! 

To use the `gowild_scraper.py` program, you need to download the actual program files from the GitHub repository.

1. Go to my GitHub repository, if you're reading this you're probably already there! 
[https://github.com/fly-metothemoon/GWsearch](https://github.com/fly-metothemoon/GWsearch).
2. Click on the green "Code" button and select "Download ZIP" to download the repository as a ZIP file.
3. Once the ZIP file is downloaded, locate it on your computer and unzip it in to a findable location on your computer.

### Running the flight search program
1. Open the terminal/command prompt following the instructions mentioned [above](#opening-your-terminal).

2. Navigate to the directory (folder) you unzipped where you have saved the `gowild_scraper.py` file using the `cd <path>` command. For example, if the file is on your desktop, you can use the following command:
* 'dir' for windows or 'ls' for mac will list all files in current directory.
   ```bash
   User> cd Desktop
   User>Desktop> cd Frontier
   ```
   **OR**
Navigate to the folder how you normally would and once inside right click and chose to 'Open in Terminal'

3. Run the program using the following command:

   ```bash
   python gowild_scraper.py -o ORIGIN -d DATES
   ```

   Replace `ORIGIN` with the IATA airport code of your origin airport (e.g., `JFK` for John F. Kennedy International Airport) and replace `DATES` with one of the following options:

   - `1` - Show flights for today.
   - `2` - Show flights for tomorrow.
   - `3` - Show flights for both today and tomorrow.

   For example, to check flights for today from JFK Airport, you would use the following command:

   ```bash
   python gowild_scraper.py -o JFK -d 1
   ```

4. The program will display the available flights and their details, including departure dates, total flight time, and prices. If there are roundtrip flights available for the next day, they will be marked with `**`. Next day return flights are only searched for if you plan on departing today. Do you want something different? Let me know!

5. After displaying the flight information, the program will list the available destinations

and ask for your input again. You can enter the index number of a destination to check for flights from your origin to that destination. Alternatively, you can enter `exit` to quit the program.

Return back to [Usage](#usage) for most information and customization.
Go [here](#example-output) to see the example output!

Happy flying and thanks for the support!

  
