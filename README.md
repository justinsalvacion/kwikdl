
# kwikdl

## Description
Downloads files from specified URLs, verifies their integrity using SHA-256 checksums, and saves them to a specified directory. It supports custom DNS resolvers and resuming interrupted downloads.

## Usage

### Command-Line Flags
- **-link**: Specifies a single download link along with an optional SHA-256 checksum and output directory.
- **-linklist**: Specifies a path to a text file containing multiple download links, each optionally followed by a SHA-256 checksum, and an output directory.

### Examples

#### Single Link Download
Download a file from a URL and verify its SHA-256 checksum:

    kwikdl.exe -link <download_link> -sha256 <expected_sha256> -outdir <output_directory>

#### Multiple Links Download
Download multiple files from a list of URLs provided in a text file:

    kwikdl.exe  -linklist <path_to_linklist> -outdir <output_directory>

Create a text file `links.txt` with the following content:

    https://example.com/file1.zip|abcdef1234567890
    https://example.com/file2.zip|1234567890abcdef` 

Run the command:
`kwikdl.exe -linklist links.txt -outdir /path/to/save` 


### Notes

-   Ensure only one of `-link` or `-linklist` is specified.
-   SHA-256 verification is not supported with `-linklist`; use the format `<download link>|<sha256>` in the link list file for checksums.
-   The program prompts for confirmation if a file already exists in the specified output directory.
