<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8" />
<title>d3 test</title>
<script src="https://cdnjs.cloudflare.com/ajax/libs/d3/3.5.6/d3.min.js" charset="utf-8"></script>
</head>

<body>
<script>
    //Width and Height
    var w = 500;
    var h = 500;

    //Create SVG Element
    var svg = d3.select("body")
                .append("svg")
                .attr("width", w)
                .attr("height", h);

    var line = svg.append("path")
            .attr("stroke","orange")
            .attr("stroke-width", 7)
            .attr("fill","none");

            line;

    //Global array
    var linedata = [];

    //random multiplier
    var randNum = 50;

    setInterval(function() {
        var random = {
            a: Math.floor(Math.random()*randNum),
            b: Math.floor(Math.random()*randNum)
        };

        linedata = [ "M 0 0 L 200 " + (100+random.a),
                     "M 150 200 L 200 " + (500+random.b)
            ];

        line.data(linedata)
                   .enter();
      
        line.attr("d", function(d) {
                return d;
            })
    }, 10);

</script>
</body>
</html>
