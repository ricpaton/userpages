[Golang] Wait For Goroutine to Finish
#####################################

:date: 2015-03-23 22:16
:modified: 2018-02-12T09:58+08:00
:tags: Go, Golang, Goroutine, Go Channels, Go sync Package
:category: Go
:summary: Use channels to wait for all goroutines to finish
:og_image: https://cdn-images-1.medium.com/max/1200/1*GWYUFH14uOVLNHY-L1tv2w.jpeg
:adsu: yes


.. contents:: This post shows two approaches to wait for all goroutines_ to
              finish.

Channel [1]_
++++++++++++

Wait for all goroutines to finish via channels_:

.. rubric:: `Run Code on Go Playground <https://play.golang.org/p/0lDZVtmpL1e>`__
   :class: align-center

.. show_github_file:: siongui userpages content/code/go-wait-goroutine-finish/sync.go
.. adsu:: 2


sync.WaitGroup [4]_
+++++++++++++++++++

Wait for all goroutines to finish via sync.WaitGroup_:

.. rubric:: `Run Code on Go Playground <https://play.golang.org/p/7jSEcLb5SyD>`__
   :class: align-center

.. code-block:: go

  package main

  import (
  	"fmt"
  	"sync"
  )

  var wg sync.WaitGroup

  func routine(site string) {
  	// Decrement the counter when the goroutine completes.
  	defer wg.Done()

  	// do something
  	fmt.Println(site)
  }

  func main() {
  	sites := []string{
  		"https://www.google.com/",
  		"https://duckduckgo.com/",
  		"https://www.bing.com/"}

  	for _, site := range sites {
  		// Increment the WaitGroup counter.
  		wg.Add(1)

  		go routine(site)
  	}

  	// wait all goroutines to finish
  	wg.Wait()
  }

.. adsu:: 3

----

Tested on: `The Go Playground`_

----

References:

.. [1] `Waiting for all goroutines to finish before ending main - Google Groups <https://groups.google.com/d/topic/golang-nuts/mNhXnWLFOo4>`_
.. [2] `DuckDuckGo <https://duckduckgo.com/>`_ Search: `golang wait for goroutine to finish <https://duckduckgo.com/?q=golang+wait+for+goroutine+to+finish>`__
.. [3] `Google <https://www.google.com/>`_ Search: `golang wait for goroutine to finish <https://www.google.com/search?q=golang+wait+for+goroutine+to+finish>`__
.. [4] `优雅の使用sync.WaitGroup - hawkingrei |  Blog <https://www.hawkingrei.com/blog/2017/08/26/gracefully-use-waitgroup/>`_

.. _channels: https://tour.golang.org/concurrency/2
.. _goroutines: https://tour.golang.org/concurrency/1
.. _sync.WaitGroup: https://golang.org/pkg/sync/#WaitGroup
.. _The Go Playground: https://play.golang.org/
