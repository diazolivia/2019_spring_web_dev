:orphan:

.. _dynamic-properties-josh:

Dynamic Properties
==================

.. raw:: html

    <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0/css/bootstrap.min.css" integrity="sha384-Gn5384xqQ1aoWXA+058RXPxPg6fy4IWvTNh0E263XmFcJlSAwiGgFAW/dAiS6JXm" crossorigin="anonymous">

    <div class="container-flex">
        <div class="row" style="height:300px">
            <div class="col-4"></div>
            <div class="col-4"></div>
            <div class="col-4"></div>
        </div>
        <div class="row" style="height:300px">
            <div class="col-4"></div>
            <div class="col-4"></div>
            <div class="col-4"></div>
        </div>
    </div>

    <script src="https://d3js.org/d3.v5.min.js"></script>
    <script>
        d3.selectAll(".col-4").style("background-color", function() {
            return "hsl(" + Math.random() * 360 + ",100%,50%)";
        });

        var data = "box";
        d3.selectAll(".col-4").data([1, 2, 3, 4, 5, 6]).append("h1").text(function(d) {
            return "Box " + d;
        });
    </script>

Refreshing the page will change the color of each of the boxes.