[![Build Status](https://travis-ci.org/theodi/euro-elections.svg)](https://travis-ci.org/theodi/euro-elections)

## European Elections 2014

The results of 2014 European Elections are due to be announced on Sunday 25th May.

This repo will contain the results by region for the UK. We're asking you to help
us collect this data, and test out [Cid](), which will validate the data when
collaborators submit it.

## Some background

This repo contains two folders, one which will contain CSV files with the votes
each party received by region, and another (as this is a [Closed list PR election](https://en.wikipedia.org/wiki/Closed_list))
which will contain the awarded seats and the details of the elected MEPs.

## Collaborating

First, [fork the repo](https://github.com/theodi/euro-elections/fork), then clone it
to your local machine either on the command line like so:

  git clone git@github.com:YOUR_USERNMAE/euro-elections.git

or using [Github for Mac](https://mac.github.com/)

Then add two CSV files in the following formats:

### Votes

The votes CSVs should live in the folder /votes and have the following columns:

* Poll Date - Date the poll took place in format YYYY-MM-DD
* Area - The name of the electoral region ([see a list of regions](https://theodi.github.io/euro-elections/regions/regions.csv))
* Area Code - The ONS code for the electoral region
* Area URL - The ONS uri for the electoral region
* Party - The name of the party
* Party ID - The Electoral Commision ID of the party ([see a list of IDs](https://theodi.github.io/euro-elections/parties/parties.csv))
* Votes - The number of votes for that party
* Ballots Rejected - The number of rejected ballots

The filename should have the format `REGION-NAME-votes.csv`

You can [see an example of what the file should look like here](https://theodi.github.io/euro-elections/votes/example-votes.csv)

### Seats

The seats CSVs should live in the folder /seats and have the following columns:

* Poll Date - Date the poll took place in format YYYY-MM-DD
* Area - The name of the electoral region ([see a list of regions](https://theodi.github.io/euro-elections/regions/regions.csv))
* Area Code - The ONS code for the electoral region
* Area URL - The ONS uri for the electoral region
* Seat - The number of the seat won
* Party - The name of the winning party
* Party ID - The Electoral Commision ID of the winning party ([see a list of IDs](https://theodi.github.io/euro-elections/parties/parties.csv))
* Name - The name of the winning candidate
* Address - The address of the winning candidate
* Postcode - The postcode of the winning candidate

The filename should have the format `REGION-NAME-seats.csv`

You can [see an example of what the file should look like here](https://theodi.github.io/euro-elections/seats/example-seats.csv)

Once you have made your changes, push them up to your fork, and [open a pull request](https://github.com/theodi/euro-elections/compare/).

Our [robots](https://github.com/theodi/cid) will then check the format of the data,
and apply a status to it. If we're happy, we'll merge the changes.

You can also validate the changes you've made before pushing by running:

  gem install cid
  cid validate

If all is well, you should see that each file is valid. If not, make the changes
and try again.
