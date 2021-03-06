# BBB-Readable-Feedback

Did you activate the 
[feedback feature](https://docs.bigbluebutton.org/2.2/customize.html#collect-feedback-from-the-users)
in BigBlueButton (BBB) but you can't read all the jibberish in the logfile? 
This is for you then.

This simple script creates humanly readable output from the feedback logs of your BigBlueButton (BBB) instance.

It has 5 simple cmd parameters you **can** use, none of which is required:

| Short | Parameter | Default | Explanation |
| :--- | :--- | :--- | :--- |
| -h | --help | None | Show this table
| -p | --path | /var/log/nginx/ | Provide the full path to the directory containing the feedback logs |
| -q | --quiet | False | If True the script won't have any output |
| -tf | --tofile | False | If True write the output to `html5-client-readable.log` |
| -pz | --parsezip | False | If True unzip `.gz` logs and parse them aswell

## Installation:

* Make sure you got Python 3 installed: `python3 -V`
* Copy the script or clone this repo to the server containing the BBB instance:
`git clone https://github.com/Helyux/BBB-Readable-Feedback.git`

## Example Use

Execute `python3 ReadFeedback.py -pz -tf`

This will parse all `html5-client.log` files in the directory `/var/log/nginx/`, even those who are already
zipped (`-pz`) and print something like this:
![Screenshot](https://user-images.githubusercontent.com/10271600/98667666-02b90300-234f-11eb-81f3-45ceedd7fe9f.png)
It'll also write the printed info to the file
`html5-client-readable.log` in the given path. (`-tf`)
