<template>
  <span :class="cssClasses">
    <slot />
  </span>
</template>

<script lang="ts">
  export default {
    name:     'VueBadge',
    props:    {
      primary:   {
        type: Boolean,
      },
      secondary: {
        type: Boolean,
      },
      tertiary:  {
        type: Boolean,
      },
      info:      {
        type: Boolean,
      },
      success:   {
        type: Boolean,
      },
      warn:      {
        type: Boolean,
      },
      danger:    {
        type: Boolean,
      },
    },
    computed: {
      cssClasses() {
        const classes: string[] = [this.$style.vueBadge];

        if (this.primary) {
          classes.push(this.$style.primary);
        } else if (this.secondary) {
          classes.push(this.$style.secondary);
        } else if (this.tertiary) {
          classes.push(this.$style.tertiary);
        } else if (this.info) {
          classes.push(this.$style.info);
        } else if (this.success) {
          classes.push(this.$style.success);
        } else if (this.warn) {
          classes.push(this.$style.warn);
        } else if (this.danger) {
          classes.push(this.$style.danger);
        }

        return classes;
      },
    },
  };
</script>

<style lang="scss" module>
  @import "../../styles";

  .vueBadge {
    display:        inline-block;
    padding:        $badge-padding;
    margin:         $badge-margin;
    font-size:      $badge-font-size;
    line-height:    $badge-line-height;
    letter-spacing: $badge-letter-spacing;
    border-radius:  $badge-border-radius;
    color:          $badge-default-color;
    background:     $badge-default-bg;
  }

  .primary {
    color:      $badge-primary-color;
    background: $badge-primary-bg;
  }

  .secondary {
    color:      $badge-secondary-color;
    background: $badge-secondary-bg;
  }

  .tertiary {
    color:      $badge-tertiary-color;
    background: $badge-tertiary-bg;
  }

  .info {
    color:      $badge-info-color;
    background: $badge-info-bg;
  }

  .success {
    color:      $badge-success-color;
    background: $badge-success-bg;
  }

  .warn {
    color:      $badge-warn-color;
    background: $badge-warn-bg;
  }

  .danger {
    color:      $badge-danger-color;
    background: $badge-danger-bg;
  }
</style>
