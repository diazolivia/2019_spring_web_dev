.. _interactive-svg-josh:

Interactive SVG
===============

.. raw:: html

    <style type="text/css">
        rect {
            fill: none;
            pointer-events: all;
        }

        circle {
            fill: none;
            stroke-width: 2.5px;
        }
    </style>

    <script src="https://d3js.org/d3.v5.min.js"></script>
    <script>
        var width = innerWidth, height = innerHeight;

        var svg = d3.select("#interactive-svg").append("svg")
            .attr("width", width)
            .attr("height", height);

        svg.append("rect")
            .attr("width", width)
            .attr("height", height)
            .on("ontouchstart" in document ? "touchmove" : "mousemove", particle);

        function particle() {
            var m = d3.mouse(this);

            svg.insert("circle", "rect")
                .attr("cx", m[0])
                .attr("cy", m[1])
                .attr("r", 1e-6)
                .style("stroke", function () {
                    return "hsl(" + Math.random() * 360 + ",100%,50%)";
                })
                .style("stroke-opacity", 1)
                .transition()
                .duration(2000)
                .ease(Math.sqrt)
                .attr("r", 100)
                .style("stroke-opacity", 1e-6)
                .remove();

            d3.event.preventDefault();
        }
    </script>