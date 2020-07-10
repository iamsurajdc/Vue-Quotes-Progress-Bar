<template>
  <div class="row">
      <div class="col-sm-12 col-md-10">
          <h3>Quotes Added</h3>
      <div class="progress">
          <!-- <div class="progress"> -->
              <div class="progress-bar" role="progressbar" area-valuenow=60 area-voluemin="0" area-voluemax="100"
                    :style="{width: (quoteCount/maxQuotes)  * 100 + '%'}">
                  {{quoteCount}}  /  {{maxQuotes}}
              </div>
          <!-- </div> -->
      </div>
      </div>
  </div>
</template>

<script>
export default {
    props: ['quoteCount','maxQuotes']
}
</script>

<style>

</style>