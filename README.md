# CPU Microcode Version

This tool builds on [CPUMicrocodes](https://github.com/platomav/CPUMicrocodes) to create a database of the latest microcode versions for each CPU and find out the latest available microcode version for the system's CPU.

## Usage

```
usage: cpu_microcode_version [-h] [-c CSV] [-d] [-i ID]

Get the current CPU microcode version

options:
  -h, --help         show this help message and exit
  -c CSV, --csv CSV  Path to the CSV database. If not present, it will be downloaded from the web.
  -d, --dont-save    Don't save the downloaded microcodes database
  -i ID, --id ID     CPU ID. By default the CPU ID will be determined using dmidecode (requires root privileges)
```

This script should run out of the box with a any fairly recent version of Python 3. To retrieve the CPU ID it uses `dmidecode` which requires root privileges to run. Therefore you'll need to run the script with sudo on most systems. Alternatively you can also pass the CPU ID as a command line argument.

On the first run, the data is automatically scraped from [CPUMicrocodes](https://github.com/platomav/CPUMicrocodes) and saved to `microcodes.csv`. To prevent downloading the file use the `-d` flag.
