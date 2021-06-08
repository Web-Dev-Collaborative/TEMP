;

bookshelf-contrib.Scopes
========================

class Books scopes: published: (q) -&gt; q.where(published: true)

Books.published().fetchAll()

bookshelf-contrib.QueryProxy
============================

Books.query().where(published: true) Books.where(published: true)

bookshelf-contrib.Migration
===========================

class Migration up: -&gt; down: -&gt;
