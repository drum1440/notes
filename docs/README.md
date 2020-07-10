# laptop_4gb     
---
## pull audio from cd      
#### install     
<pre>
sudo apt install sound-juicer
</pre>

- put cd in before starting program     
- settings: ensure output goes to /Music/[appropriate folder]     
- run program with      

<pre>
sound-juicer
</pre>
- select desired tracks, then "extract"     

## after extracting audio from cd, write to mp3 files     
#### install     
<pre>
sudo apt install soundconverter
</pre>

- run program with      

<pre>
soundconverter
</pre>
- click on previously extracted files with “add file” (from previous step, above), “convert”     
- rm .ogg files when done     


---
## general Linux commands
<pre>
tar -cvf name-of-archive.tar /path/to/directory-or-file
tar -cvf name-of-archive.tar *
</pre>

- show current release     

<pre>
lsb_release -a
</pre>

- this renames all files in folder from 'a b.txt' to a_b.txt     

<pre>
for file in *; do mv "$file" `echo $file | tr ' ' '_'` ; done
</pre>

---
## mkdocs

https://www.mkdocs.org/

#### install
<pre>
sudo apt-get install mkdocs
</pre>


#### Project layout     

    mkdocs.yml    # The configuration file.     
    docs/
        index.md  # The documentation homepage.
        ...       # Other markdown pages, images and other files.     


#### how to implement

<pre>
cd Documents
mkdir z1
cd z1

mkdocs new mkdocs01     
cd mkdocs01     

mkdocs serve
</pre>

#### when you're ready to deploy...

<pre>
mkdocs build
(base) brad@brad-U50F:~/Documents/z1/mkdocs01$ pwd
/home/brad/Documents/z1/mkdocs01

cp * -R ../../notes
cd ../../notes
git add .
git commit -m "notes"
git push
mkdocs gh-deploy
</pre>

.
.
INFO    -  Your documentation should shortly be available at: https://drum1440.github.io/notes/      


---
## git (laptop 4g)

- create "notes" in GitHub client     

<pre>     
cd Documents     
git clone https://github.com/drum1440/notes.git     
cd notes     
</pre>


#### regenerate ssh key in Git     
https://docs.github.com/en/github/authenticating-to-github/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent     
<pre>
ssh-keygen -t rsa -b 4096 -C "my Hotmail email"     
generate a new SSH key     
eval "$(ssh-agent -s)"     
ssh-add ~/.ssh/id_rsa     
Add the SSH key to your GitHub account     
( in Settings, SSH and GPG keys )     
copy id_rsa.pub data (starts with ssh-rsa...) into GitHub key box
</pre>

end out of eval "$(ssh-agent -s)" as soon as you're done.

