# s3arch

Utility for creating archival backups of S3 buckets.

## Installation

    pip install s3arch

AWS key and secret can be specified by the `-k` and `-s` command line
arguments, `AWS_ACCESS_KEY_ID` and `AWS_SECRET_ACCESS_KEY` environment variables, or [`.boto` configuration files](http://docs.pythonboto.org/en/latest/boto_config_tut.html).

## Example

Backup and compress *myawesomebucket* bucket to ~/Downloads:

    s3arch -o ~/Downloads -z myawesomebucket

## Usage

    usage: s3arch.py [-h] [-k KEY] [-s SECRET] [-o PATH]
                     [-p PREFIX] [-v] [-z]
                     BUCKET [BUCKET ...]

    positional arguments:
      BUCKET                buckets to archive

    optional arguments:
      -h, --help            show this help message and exit
      -k KEY, --key KEY     S3 key
      -s SECRET, --secret SECRET
                            S3 secret key
      -o PATH, --outputdir PATH
                            directory in which the archives will be placed
                            (default is current directory)
      -p PREFIX, --prefix PREFIX
                            prefix added to the local bucket directory name (and
                            tar archive if -z)
      -v                    verbose output to stdout
      -z                    compress backup with gzip
