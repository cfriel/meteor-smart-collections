# Meteor Smart Collections [![Build Status](https://travis-ci.org/arunoda/meteor-smart-collections.png?branch=master)](https://travis-ci.org/arunoda/meteor-smart-collections)

This is a complete re-write of the MongoDB Collection implementation for Meteor. Designed with following 3 areas in mind

* Speed
* Effieciency (Memory & CPU)
* Scalability

> This is not a toy project! But a complete Collection replacement with a [well tested](https://github.com/arunoda/meteor-smart-collections/blob/master/test_cases.todo) source code. Still we **might** have bugs :)

### [Click here for implementation details of Smart Collections](http://meteorhacks.com/introducing-smart-collections.html)

## Usage

Install Smart Collections from Atmosphere
    
    mrt add smart-collections

Replace `Meteor.Collection` with `Meteor.SmartCollection`. Just that!

eg:-

    //old code
    Posts = new Meteor.Collection('posts');

    //with smart collections
    Posts = new Meteor.SmartCollection('posts');

## Compatibility

* Almost compatible with exiting `Collection` [API](http://docs.meteor.com/#collections)
* But server side `Cursor.observe()` does not exists
* `_id` must be a `String` (will support `ObjectID` and `numbers` soon)

## Scalability

* Designed to be scaled with mongodb [`oplog`](http://docs.mongodb.org/manual/core/replica-set-oplog/)
* Not implemented yet! (will start after we've fixed most critical bugs)