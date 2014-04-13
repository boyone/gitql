Gitql [![Build Status](https://travis-ci.org/cloudson/gitql.png)](https://travis-ci.org/cloudson/gitql)
===============

Gitql is a Git query language.



See more [here](https://asciinema.org/a/8863)

## Install

- `go get -d github.com/cloudson/gitql`
- `cd $GOPATH/src/github.com/cloudson/gitql`
- `make install`
- `export LD_LIBRARY_PATH=$PWD/libgit2/install/lib`
- `export PKG_CONFIG_PATH=$PWD/libgit2/install/lib/pkgconfig`

## Examples 

`gitql -q "your query" `

Look the table of commits:

| commits | 
| ---------| 
| author |
| author_email | 
| committer |
| committer_email |
| hash | 
| date |
| message | 
| full_message | 

(see more tables [here](./tables.md))

You can do:   
* `select hash, author, message from commits`  
* `select hash, message from commits where 'hell' in full_message or 'Fuck' in full_message`  
* `select hash, message, author_email from commits where author = 'cloudson'`  
* `select date, message from commits where date < '2014-04-10' `  
* :warning: `select message from commits where 'hell' in message order by date asc`   


Notes:   
* Gitql dont want kill `git log` :sweat_smile: . It was created just for science!!  
* It's  read-only. Nothing about delete, insert or update commits :stuck_out_tongue_closed_eyes:  
* It's ispired from [textql](https://github.com/dinedal/textql)  
