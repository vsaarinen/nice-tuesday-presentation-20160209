# Presentation: Building the flow of refugees to Europe visualization

A presentation about building a [visualization](http://lucify.com/the-flow-towards-europe/) about the European refugee crisis. The presentation illustrates the choices and dead ends encountered along the way. Built using [Reveal.js](https://github.com/hakimel/reveal.js/).

### Authors

- [Juho Ojala](https://twitter.com/ojalajuho)
- [Ville Saarinen](https://twitter.com/vsaarinen)

### Presented at

- [Nice Tuesday Helsinki](http://www.nicetuesday.fi/) (9.2.2016)

### Setup

This presentation displays 10 copies of the visualization at different points during its development process. It requires checking out 10 different versions of the visualization and running them on specific ports, which are then displayed via iframe in this presentation.

Get the [lucify-refugees code](https://github.com/lucified/lucify-refugees) running on your local machine. Make ten snapshots of the code at different commits (hashes below) and serve these ten different versions locally on ports 3000, 3002, ...3018. I recommend using Git's new [worktree](https://git-scm.com/docs/git-worktree) command for this:

```shell
$ cd <path-to-lucify-refugees>
$ mkdir versions
$ git worktree add --detach versions/01-first-version master
$ cd versions/01-first-version
$ git checkout 84e9b97516adcdb349ed56fe679eea99750f7055
<set up the repo with npm install, etc.>
```

Setting up code to run usually consists of `npm install`, `./prepare.sh && node src/scripts/prepare-asylum-data.js` (in early versions) and `bundle install` (from a certain point on).

Repeat the last three steps for the remaining nine versions. The version commit hashes are:

1. First version: `84e9b97516adcdb349ed56fe679eea99750f7055`
2. Center point vs. random point: `0f83c5efda2d8c24f7947293b3f7b594f21cd343`
3. Refugee data added: `345f2f99d26bcbac3c08a0d7c30eb1f7814edcdf`
4. Added a spread: `50045bbbd0240611cd0740d25b7f4980793b662f`
5. Permanent random point: `56914ce4f9f30374b91d99a0c8de91fc92f08612`
6. Added bar graphs: `3807170adee60bb12c85d9feddda4ac96715085c`
7. Added tails + legend + country labels: `3cdefe8bd2c2c444e099f72cfb0b14fe1b73067d`
8. Highlight refugees + country labels on hover: `c9de83875de510df4dd8d5a6264fef050d44e190`
9. Scrolling through time: `df2446ddb3bb9c6cd099d0ade94dbcd76956b039`
10. Country-specific hover data: `294d3966c0db2ff76852fb5f5563531c4662f52d`

Once all of these have been set up, start the HTTP server in each repo with `gulp`. If you start the server in the order above, the ports will be the correct ones (3000, 3002...) by default. Then open `index.html` from this repo.
