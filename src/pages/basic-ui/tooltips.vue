<template>

  <section class="tooltips">
    <div class="page-header">
      <h3 class="page-title">
        Tooltips & Popover
      </h3>
      <nav aria-label="breadcrumb">
        <ol class="breadcrumb">
          <li class="breadcrumb-item"><a href="javascript:void(0);">UI Elements</a></li>
          <li class="breadcrumb-item active" aria-current="page">Tooltips</li>
        </ol>
      </nav>
    </div>
    <div class="row">
      <div class="col-xl-6 col-md-12 grid-margin stretch-card">
        <div class="card">
          <div class="card-body">
            <h4 class="card-title">Basic tooltip</h4>
            <p class="card-description">Basic tooltip demo that appears on hover</p>
            <p>Hover the below button for interactive demo</p>
            <b-btn v-b-tooltip.html.top
             title="I'm a tooltip!"
             variant="primary">
              Hover Me
            </b-btn>
          </div>
          <div class="card-body">
            <h4 class="card-title">Tooltip positions</h4>
            <p class="card-description">Add attribute <code>"v-b-tooltip.html.*"</code> prop for desired position</p>
            <div class="template-demo">
              <b-btn v-b-tooltip.html.top
               title="I'm a tooltip!"
               variant="warning">
                Top
              </b-btn>
              <b-btn v-b-tooltip.html.right
               title="I'm a tooltip!"
               variant="secondary">
                Right
              </b-btn>
              <b-btn v-b-tooltip.html.bottom
               title="I'm a tooltip!"
               variant="info">
                Bottom
              </b-btn>
              <b-btn v-b-tooltip.html.left
               title="I'm a tooltip!"
               variant="danger">
                Left
              </b-btn>
            </div>
          </div>
        </div>
      </div>
      <div class="col-xl-6 col-md-12 grid-margin stretch-card">
        <div class="card">
          <div class="card-body">
            <h4 class="card-title">Popover positions</h4>
            <p class="card-description">Add attribute <code>:placement="*placement"</code> for desired position</p>
            <b-row>
              <b-col md="4" class="py-2" v-for="placement in placements" :key="placement">
                <b-btn :id="'exPopover1-'+placement" variant="primary">
                  {{ placement }}
                </b-btn>
                <b-popover :target="'exPopover1-'+placement" :placement="placement" title="Popover!" triggers="hover focus" :content="`Placement ${placement}`">
                </b-popover>
              </b-col>
            </b-row>
          </div>
        </div>
      </div>
    </div>
  </section>

</template>

<script>
export default {
  name: 'tooltips',
  data () {
    return {
      placements: [
        'topright', 'top', 'topleft',
        'bottomright', 'bottom', 'bottomleft',
        'righttop', 'right', 'lefttop',
        'rightbottom', 'left', 'leftbottom'
      ]
    }
  }
}
</script>