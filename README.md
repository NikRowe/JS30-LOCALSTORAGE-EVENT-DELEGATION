# JS30 LocalStorage & Event Delegation
Exercise 15 in WesBos' JavaScript30 tutorials. 

This one took me most of the day as well, granted I was running off of 3hours of sleep form the night before and my thought process was quite possibly corrupted. 

Coming from a newer boot camp experience with React.js as the core it was interesting to see how vanilla + html handled local state. It certainly feels as if these basics throughout the js30 tutorials are really helping strengthen core concepts. 

I actually ended up doing something similar to this app layout on day 14 for my "bonus/extra" steps, without realizing Wes was going to cover it today. Mine was not quite as smooth but I was using one function to update the HTML for the user to see and others to update different data. 

I took it a step further as always and accepted Wes' challenge to create 3 buttons (remove, reset, check-all). Remove was the hardest logic for me to come up with from scratch.
I chose to filter() the items array for items that weren't checked then update the items array to the newly filtered array, thus removing the checked items. 
    
    function removeItem(e) {
      e.preventDefault()
      const filteredItems = items.filter((item, i) => {
        return !item.done
      })

      items = filteredItems
      populateList(items, itemsList)
      localStorage.setItem('items', JSON.stringify(items))
    }

I found check-all to be a fun one, it didn't stump me but took some extra thinking for a good UX. We obviously needed the button to check all items as described, however I wanted it to check all <i>remaining</i> items if the user had already checked some. I also wanted to <i>un-check</i> all items if all items were already checked. 



<a href="https://nikrowedevjs30-localstorage-event-delegation.netlify.app/">Demo</a>