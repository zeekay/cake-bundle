require 'shortcake'

use 'cake-outdated'
use 'cake-publish'
use 'cake-version'
use 'cake-yarn'

use (require './') entry: 'src/index.coffee'

task 'bootstrap', 'build project', ->
  handroll = require 'handroll'

  bundle = yield handroll.bundle
    entry:    'src/index.coffee'
    external: true

  yield bundle.write format: 'cjs'
  yield bundle.write format: 'es'

task 'build', 'build project', ->
  bundle.write
    entry:   'src/index.coffee'
    formats: ['cjs', 'es']

task 'clean', 'clean project', ->
  exec 'rm -rf dist'
