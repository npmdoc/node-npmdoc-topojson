# api documentation for  [topojson (v3.0.0)](https://github.com/topojson/topojson)  [![npm package](https://img.shields.io/npm/v/npmdoc-topojson.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-topojson) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-topojson.svg)](https://travis-ci.org/npmdoc/node-npmdoc-topojson)
#### An extension to GeoJSON that encodes topology.

[![NPM](https://nodei.co/npm/topojson.png?downloads=true)](https://www.npmjs.com/package/topojson)

[![apidoc](https://npmdoc.github.io/node-npmdoc-topojson/build/screenCapture.buildNpmdoc.browser._2Fhome_2Ftravis_2Fbuild_2Fnpmdoc_2Fnode-npmdoc-topojson_2Ftmp_2Fbuild_2Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-topojson/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-topojson/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-topojson/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "Mike Bostock",
        "url": "https://bost.ocks.org/mike"
    },
    "bin": {
        "geo2topo": "node_modules/topojson-server/bin/geo2topo",
        "toposimplify": "node_modules/topojson-simplify/bin/toposimplify",
        "topo2geo": "node_modules/topojson-client/bin/topo2geo",
        "topomerge": "node_modules/topojson-client/bin/topomerge",
        "topoquantize": "node_modules/topojson-client/bin/topoquantize"
    },
    "browser": "dist/topojson.js",
    "bugs": {
        "url": "https://github.com/topojson/topojson/issues"
    },
    "dependencies": {
        "topojson-client": "3.0.0",
        "topojson-server": "3.0.0",
        "topojson-simplify": "3.0.0"
    },
    "description": "An extension to GeoJSON that encodes topology.",
    "devDependencies": {
        "package-preamble": "0.0",
        "rollup": "0.41",
        "rollup-plugin-ascii": "0.0",
        "rollup-plugin-node-resolve": "2",
        "tape": "4",
        "uglify-js": "2"
    },
    "directories": {},
    "dist": {
        "shasum": "c2aca1b76435e801dce3f229586bbd5767115ce3",
        "tarball": "https://registry.npmjs.org/topojson/-/topojson-3.0.0.tgz"
    },
    "gitHead": "ccd0bcad70bb837d27d14b9524c0bffb3ae41d19",
    "homepage": "https://github.com/topojson/topojson",
    "jsnext:main": "index",
    "keywords": [
        "topojson",
        "geojson"
    ],
    "license": "BSD-3-Clause",
    "main": "dist/topojson.node.js",
    "maintainers": [
        {
            "name": "mbostock",
            "email": "mbostock@gmail.com"
        },
        {
            "name": "jasondavies",
            "email": "jason@jasondavies.com"
        }
    ],
    "module": "index",
    "name": "topojson",
    "optionalDependencies": {},
    "readme": "ERROR: No README data found!",
    "repository": {
        "type": "git",
        "url": "git+https://github.com/topojson/topojson.git"
    },
    "scripts": {
        "postpublish": "git push && git push --tags && cp -v README.md LICENSE.md dist/topojson.js dist/topojson.min.js ../topojson-bower && cd ../topojson-bower && git add README.md LICENSE.md topojson.js topojson.min.js && git commit -m \"${npm_package_version}\" && git tag -am \"${npm_package_version}\" v${npm_package_version} && git push && git push --tags && cd - && cp dist/topojson.js ../d3.github.com/topojson.v3.js && cp dist/topojson.min.js ../d3.github.com/topojson.v3.min.js && cd ../d3.github.com && git add topojson.v3.js topojson.v3.min.js && git commit -m \"topojson ${npm_package_version}\" && git push && cd - && zip -j dist/topojson.zip -- LICENSE.md README.md dist/topojson.js dist/topojson.min.js",
        "prepublish": "npm run test && rollup -c --banner \"$(preamble)\" -f umd -n topojson -o dist/topojson.js -- index.js && uglifyjs --preamble \"$(preamble)\" dist/topojson.js -c negate_iife=false -m -o dist/topojson.min.js",
        "pretest": "rm -rf dist && mkdir dist && node rollup.node",
        "test": "tape 'test/**/*-test.js'"
    },
    "version": "3.0.0"
}
```



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module topojson](#apidoc.module.topojson)
1.  [function <span class="apidocSignatureSpan">topojson.</span>bbox (topology)](#apidoc.element.topojson.bbox)
1.  [function <span class="apidocSignatureSpan">topojson.</span>feature (topology, o)](#apidoc.element.topojson.feature)
1.  [function <span class="apidocSignatureSpan">topojson.</span>filter (topology, filter)](#apidoc.element.topojson.filter)
1.  [function <span class="apidocSignatureSpan">topojson.</span>filterAttached (topology)](#apidoc.element.topojson.filterAttached)
1.  [function <span class="apidocSignatureSpan">topojson.</span>filterAttachedWeight (topology, minWeight, weight)](#apidoc.element.topojson.filterAttachedWeight)
1.  [function <span class="apidocSignatureSpan">topojson.</span>filterWeight (topology, minWeight, weight)](#apidoc.element.topojson.filterWeight)
1.  [function <span class="apidocSignatureSpan">topojson.</span>merge (topology)](#apidoc.element.topojson.merge)
1.  [function <span class="apidocSignatureSpan">topojson.</span>mergeArcs (topology, objects)](#apidoc.element.topojson.mergeArcs)
1.  [function <span class="apidocSignatureSpan">topojson.</span>mesh (topology)](#apidoc.element.topojson.mesh)
1.  [function <span class="apidocSignatureSpan">topojson.</span>meshArcs (topology, object$$1, filter)](#apidoc.element.topojson.meshArcs)
1.  [function <span class="apidocSignatureSpan">topojson.</span>neighbors (objects)](#apidoc.element.topojson.neighbors)
1.  [function <span class="apidocSignatureSpan">topojson.</span>planarRingArea (ring)](#apidoc.element.topojson.planarRingArea)
1.  [function <span class="apidocSignatureSpan">topojson.</span>planarTriangleArea (triangle)](#apidoc.element.topojson.planarTriangleArea)
1.  [function <span class="apidocSignatureSpan">topojson.</span>presimplify (topology, weight)](#apidoc.element.topojson.presimplify)
1.  [function <span class="apidocSignatureSpan">topojson.</span>quantile (topology, p)](#apidoc.element.topojson.quantile)
1.  [function <span class="apidocSignatureSpan">topojson.</span>quantize (topology, transform)](#apidoc.element.topojson.quantize)
1.  [function <span class="apidocSignatureSpan">topojson.</span>simplify (topology, minWeight)](#apidoc.element.topojson.simplify)
1.  [function <span class="apidocSignatureSpan">topojson.</span>sphericalRingArea (ring, interior)](#apidoc.element.topojson.sphericalRingArea)
1.  [function <span class="apidocSignatureSpan">topojson.</span>sphericalTriangleArea (t)](#apidoc.element.topojson.sphericalTriangleArea)
1.  [function <span class="apidocSignatureSpan">topojson.</span>topology (objects, quantization)](#apidoc.element.topojson.topology)
1.  [function <span class="apidocSignatureSpan">topojson.</span>transform (transform)](#apidoc.element.topojson.transform)
1.  [function <span class="apidocSignatureSpan">topojson.</span>untransform (transform)](#apidoc.element.topojson.untransform)



# <a name="apidoc.module.topojson"></a>[module topojson](#apidoc.module.topojson)

#### <a name="apidoc.element.topojson.bbox"></a>[function <span class="apidocSignatureSpan">topojson.</span>bbox (topology)](#apidoc.element.topojson.bbox)
- description and source-code
```javascript
bbox = function (topology) {
  var t = transform(topology.transform), key,
      x0 = Infinity, y0 = x0, x1 = -x0, y1 = -x0;

  function bboxPoint(p) {
    p = t(p);
    if (p[0] < x0) x0 = p[0];
    if (p[0] > x1) x1 = p[0];
    if (p[1] < y0) y0 = p[1];
    if (p[1] > y1) y1 = p[1];
  }

  function bboxGeometry(o) {
    switch (o.type) {
      case "GeometryCollection": o.geometries.forEach(bboxGeometry); break;
      case "Point": bboxPoint(o.coordinates); break;
      case "MultiPoint": o.coordinates.forEach(bboxPoint); break;
    }
  }

  topology.arcs.forEach(function(arc) {
    var i = -1, n = arc.length, p;
    while (++i < n) {
      p = t(arc[i], i);
      if (p[0] < x0) x0 = p[0];
      if (p[0] > x1) x1 = p[0];
      if (p[1] < y0) y0 = p[1];
      if (p[1] > y1) y1 = p[1];
    }
  });

  for (key in topology.objects) {
    bboxGeometry(topology.objects[key]);
  }

  return [x0, y0, x1, y1];
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.topojson.feature"></a>[function <span class="apidocSignatureSpan">topojson.</span>feature (topology, o)](#apidoc.element.topojson.feature)
- description and source-code
```javascript
feature = function (topology, o) {
  return o.type === "GeometryCollection"
      ? {type: "FeatureCollection", features: o.geometries.map(function(o) { return feature$1(topology, o); })}
      : feature$1(topology, o);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.topojson.filter"></a>[function <span class="apidocSignatureSpan">topojson.</span>filter (topology, filter)](#apidoc.element.topojson.filter)
- description and source-code
```javascript
filter = function (topology, filter) {
  var oldObjects = topology.objects,
      newObjects = {},
      key;

  if (filter == null) filter = filterTrue;

  function filterGeometry(input) {
    var output, arcs;
    switch (input.type) {
      case "Polygon": {
        arcs = filterRings(input.arcs);
        output = arcs ? {type: "Polygon", arcs: arcs} : {type: null};
        break;
      }
      case "MultiPolygon": {
        arcs = input.arcs.map(filterRings).filter(filterIdentity);
        output = arcs.length ? {type: "MultiPolygon", arcs: arcs} : {type: null};
        break;
      }
      case "GeometryCollection": {
        arcs = input.geometries.map(filterGeometry).filter(filterNotNull);
        output = arcs.length ? {type: "GeometryCollection", geometries: arcs} : {type: null};
        break;
      }
      default: return input;
    }
    if (input.id != null) output.id = input.id;
    if (input.bbox != null) output.bbox = input.bbox;
    if (input.properties != null) output.properties = input.properties;
    return output;
  }

  function filterRings(arcs) {
    return arcs.length && filterExteriorRing(arcs[0]) // if the exterior is small, ignore any holes
        ? [arcs[0]].concat(arcs.slice(1).filter(filterInteriorRing))
        : null;
  }

  function filterExteriorRing(ring) {
    return filter(ring, false);
  }

  function filterInteriorRing(ring) {
    return filter(ring, true);
  }

  for (key in oldObjects) {
    newObjects[key] = filterGeometry(oldObjects[key]);
  }

  return prune({
    type: "Topology",
    bbox: topology.bbox,
    transform: topology.transform,
    objects: newObjects,
    arcs: topology.arcs
  });
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.topojson.filterAttached"></a>[function <span class="apidocSignatureSpan">topojson.</span>filterAttached (topology)](#apidoc.element.topojson.filterAttached)
- description and source-code
```javascript
filterAttached = function (topology) {
  var uniqueRingByArc = {}, // arc index -> index of unique associated ring, or -1 if used by multiple rings
      ringIndex = 0,
      name;

  function testGeometry(o) {
    switch (o.type) {
      case "GeometryCollection": o.geometries.forEach(testGeometry); break;
      case "Polygon": testArcs(o.arcs); break;
      case "MultiPolygon": o.arcs.forEach(testArcs); break;
    }
  }

  function testArcs(arcs) {
    for (var i = 0, n = arcs.length; i < n; ++i, ++ringIndex) {
      for (var ring = arcs[i], j = 0, m = ring.length; j < m; ++j) {
        var arc = ring[j];
        if (arc < 0) arc = ~arc;
        var uniqueRing = uniqueRingByArc[arc];
        if (uniqueRing >= 0 && uniqueRing !== ringIndex) uniqueRingByArc[arc] = -1;
        else uniqueRingByArc[arc] = ringIndex;
      }
    }
  }

  for (name in topology.objects) {
    testGeometry(topology.objects[name]);
  }

  return function(ring) {
    for (var j = 0, m = ring.length, arc; j < m; ++j) {
      if (arc = ring[j], uniqueRingByArc[arc < 0 ? ~arc : arc] < 0) {
        return true;
      }
    }
    return false;
  };
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.topojson.filterAttachedWeight"></a>[function <span class="apidocSignatureSpan">topojson.</span>filterAttachedWeight (topology, minWeight, weight)](#apidoc.element.topojson.filterAttachedWeight)
- description and source-code
```javascript
filterAttachedWeight = function (topology, minWeight, weight) {
  var a = filterAttached(topology),
      w = filterWeight(topology, minWeight, weight);
  return function(ring, interior) {
    return a(ring, interior) || w(ring, interior);
  };
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.topojson.filterWeight"></a>[function <span class="apidocSignatureSpan">topojson.</span>filterWeight (topology, minWeight, weight)](#apidoc.element.topojson.filterWeight)
- description and source-code
```javascript
filterWeight = function (topology, minWeight, weight) {
  minWeight = minWeight == null ? Number.MIN_VALUE : +minWeight;

  if (weight == null) weight = planarRingArea;

  return function(ring, interior) {
    return weight(topojsonClient.feature(topology, {type: "Polygon", arcs: [ring]}).geometry.coordinates[0], interior) >= minWeight
;
  };
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.topojson.merge"></a>[function <span class="apidocSignatureSpan">topojson.</span>merge (topology)](#apidoc.element.topojson.merge)
- description and source-code
```javascript
merge = function (topology) {
  return object(topology, mergeArcs.apply(this, arguments));
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.topojson.mergeArcs"></a>[function <span class="apidocSignatureSpan">topojson.</span>mergeArcs (topology, objects)](#apidoc.element.topojson.mergeArcs)
- description and source-code
```javascript
function mergeArcs(topology, objects) {
  var polygonsByArc = {},
      polygons = [],
      groups = [];

  objects.forEach(geometry);

  function geometry(o) {
    switch (o.type) {
      case "GeometryCollection": o.geometries.forEach(geometry); break;
      case "Polygon": extract(o.arcs); break;
      case "MultiPolygon": o.arcs.forEach(extract); break;
    }
  }

  function extract(polygon) {
    polygon.forEach(function(ring) {
      ring.forEach(function(arc) {
        (polygonsByArc[arc = arc < 0 ? ~arc : arc] || (polygonsByArc[arc] = [])).push(polygon);
      });
    });
    polygons.push(polygon);
  }

  function area(ring) {
    return planarRingArea(object(topology, {type: "Polygon", arcs: [ring]}).coordinates[0]);
  }

  polygons.forEach(function(polygon) {
    if (!polygon._) {
      var group = [],
          neighbors = [polygon];
      polygon._ = 1;
      groups.push(group);
      while (polygon = neighbors.pop()) {
        group.push(polygon);
        polygon.forEach(function(ring) {
          ring.forEach(function(arc) {
            polygonsByArc[arc < 0 ? ~arc : arc].forEach(function(polygon) {
              if (!polygon._) {
                polygon._ = 1;
                neighbors.push(polygon);
              }
            });
          });
        });
      }
    }
  });

  polygons.forEach(function(polygon) {
    delete polygon._;
  });

  return {
    type: "MultiPolygon",
    arcs: groups.map(function(polygons) {
      var arcs = [], n;

      // Extract the exterior (unique) arcs.
      polygons.forEach(function(polygon) {
        polygon.forEach(function(ring) {
          ring.forEach(function(arc) {
            if (polygonsByArc[arc < 0 ? ~arc : arc].length < 2) {
              arcs.push(arc);
            }
          });
        });
      });

      // Stitch the arcs into one or more rings.
      arcs = stitch(topology, arcs);

      // If more than one ring is returned,
      // at most one of these rings can be the exterior;
      // choose the one with the greatest absolute area.
      if ((n = arcs.length) > 1) {
        for (var i = 1, k = area(arcs[0]), ki, t; i < n; ++i) {
          if ((ki = area(arcs[i])) > k) {
            t = arcs[0], arcs[0] = arcs[i], arcs[i] = t, k = ki;
          }
        }
      }

      return arcs;
    })
  };
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.topojson.mesh"></a>[function <span class="apidocSignatureSpan">topojson.</span>mesh (topology)](#apidoc.element.topojson.mesh)
- description and source-code
```javascript
mesh = function (topology) {
  return object(topology, meshArcs.apply(this, arguments));
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.topojson.meshArcs"></a>[function <span class="apidocSignatureSpan">topojson.</span>meshArcs (topology, object$$1, filter)](#apidoc.element.topojson.meshArcs)
- description and source-code
```javascript
function meshArcs(topology, object$$1, filter) {
  var arcs, i, n;
  if (arguments.length > 1) arcs = extractArcs(topology, object$$1, filter);
  else for (i = 0, arcs = new Array(n = topology.arcs.length); i < n; ++i) arcs[i] = i;
  return {type: "MultiLineString", arcs: stitch(topology, arcs)};
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.topojson.neighbors"></a>[function <span class="apidocSignatureSpan">topojson.</span>neighbors (objects)](#apidoc.element.topojson.neighbors)
- description and source-code
```javascript
neighbors = function (objects) {
  var indexesByArc = {}, // arc index -> array of object indexes
      neighbors = objects.map(function() { return []; });

  function line(arcs, i) {
    arcs.forEach(function(a) {
      if (a < 0) a = ~a;
      var o = indexesByArc[a];
      if (o) o.push(i);
      else indexesByArc[a] = [i];
    });
  }

  function polygon(arcs, i) {
    arcs.forEach(function(arc) { line(arc, i); });
  }

  function geometry(o, i) {
    if (o.type === "GeometryCollection") o.geometries.forEach(function(o) { geometry(o, i); });
    else if (o.type in geometryType) geometryType[o.type](o.arcs, i);
  }

  var geometryType = {
    LineString: line,
    MultiLineString: polygon,
    Polygon: polygon,
    MultiPolygon: function(arcs, i) { arcs.forEach(function(arc) { polygon(arc, i); }); }
  };

  objects.forEach(geometry);

  for (var i in indexesByArc) {
    for (var indexes = indexesByArc[i], m = indexes.length, j = 0; j < m; ++j) {
      for (var k = j + 1; k < m; ++k) {
        var ij = indexes[j], ik = indexes[k], n;
        if ((n = neighbors[ij])[i = bisect(n, ik)] !== ik) n.splice(i, 0, ik);
        if ((n = neighbors[ik])[i = bisect(n, ij)] !== ij) n.splice(i, 0, ij);
      }
    }
  }

  return neighbors;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.topojson.planarRingArea"></a>[function <span class="apidocSignatureSpan">topojson.</span>planarRingArea (ring)](#apidoc.element.topojson.planarRingArea)
- description and source-code
```javascript
function planarRingArea(ring) {
  var i = -1, n = ring.length, a, b = ring[n - 1], area = 0;
  while (++i < n) a = b, b = ring[i], area += a[0] * b[1] - a[1] * b[0];
  return Math.abs(area) / 2;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.topojson.planarTriangleArea"></a>[function <span class="apidocSignatureSpan">topojson.</span>planarTriangleArea (triangle)](#apidoc.element.topojson.planarTriangleArea)
- description and source-code
```javascript
function planarTriangleArea(triangle) {
  var a = triangle[0], b = triangle[1], c = triangle[2];
  return Math.abs((a[0] - c[0]) * (b[1] - a[1]) - (a[0] - b[0]) * (c[1] - a[1])) / 2;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.topojson.presimplify"></a>[function <span class="apidocSignatureSpan">topojson.</span>presimplify (topology, weight)](#apidoc.element.topojson.presimplify)
- description and source-code
```javascript
presimplify = function (topology, weight) {
  var point = topology.transform ? topojsonClient.transform(topology.transform) : copy,
      heap = newHeap();

  if (weight == null) weight = planarTriangleArea;

  var arcs = topology.arcs.map(function(arc) {
    var triangles = [],
        maxWeight = 0,
        triangle,
        i,
        n;

    arc = arc.map(point);

    for (i = 1, n = arc.length - 1; i < n; ++i) {
      triangle = [arc[i - 1], arc[i], arc[i + 1]];
      triangle[1][2] = weight(triangle);
      triangles.push(triangle);
      heap.push(triangle);
    }

    // Always keep the arc endpoints!
    arc[0][2] = arc[n][2] = Infinity;

    for (i = 0, n = triangles.length; i < n; ++i) {
      triangle = triangles[i];
      triangle.previous = triangles[i - 1];
      triangle.next = triangles[i + 1];
    }

    while (triangle = heap.pop()) {
      var previous = triangle.previous,
          next = triangle.next;

      // If the weight of the current point is less than that of the previous
      // point to be eliminated, use the latter’s weight instead. This ensures
      // that the current point cannot be eliminated without eliminating
      // previously- eliminated points.
      if (triangle[1][2] < maxWeight) triangle[1][2] = maxWeight;
      else maxWeight = triangle[1][2];

      if (previous) {
        previous.next = next;
        previous[2] = triangle[2];
        update(previous);
      }

      if (next) {
        next.previous = previous;
        next[0] = triangle[0];
        update(next);
      }
    }

    return arc;
  });

  function update(triangle) {
    heap.remove(triangle);
    triangle[1][2] = weight(triangle);
    heap.push(triangle);
  }

  return {
    type: "Topology",
    bbox: topology.bbox,
    objects: topology.objects,
    arcs: arcs
  };
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.topojson.quantile"></a>[function <span class="apidocSignatureSpan">topojson.</span>quantile (topology, p)](#apidoc.element.topojson.quantile)
- description and source-code
```javascript
quantile = function (topology, p) {
  var array = [];

  topology.arcs.forEach(function(arc) {
    arc.forEach(function(point) {
      if (isFinite(point[2])) { // Ignore endpoints, whose weight is Infinity.
        array.push(point[2]);
      }
    });
  });

  return array.length && quantile$1(array.sort(descending), p);
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.topojson.quantize"></a>[function <span class="apidocSignatureSpan">topojson.</span>quantize (topology, transform)](#apidoc.element.topojson.quantize)
- description and source-code
```javascript
quantize = function (topology, transform) {
  if (topology.transform) throw new Error("already quantized");

  if (!transform || !transform.scale) {
    if (!((n = Math.floor(transform)) >= 2)) throw new Error("n must be ≥2");
    box = topology.bbox || bbox(topology);
    var x0 = box[0], y0 = box[1], x1 = box[2], y1 = box[3], n;
    transform = {scale: [x1 - x0 ? (x1 - x0) / (n - 1) : 1, y1 - y0 ? (y1 - y0) / (n - 1) : 1], translate: [x0, y0]};
  } else {
    box = topology.bbox;
  }

  var t = untransform(transform), box, key, inputs = topology.objects, outputs = {};

  function quantizePoint(point) {
    return t(point);
  }

  function quantizeGeometry(input) {
    var output;
    switch (input.type) {
      case "GeometryCollection": output = {type: "GeometryCollection", geometries: input.geometries.map(quantizeGeometry)}; break
;
      case "Point": output = {type: "Point", coordinates: quantizePoint(input.coordinates)}; break;
      case "MultiPoint": output = {type: "MultiPoint", coordinates: input.coordinates.map(quantizePoint)}; break;
      default: return input;
    }
    if (input.id != null) output.id = input.id;
    if (input.bbox != null) output.bbox = input.bbox;
    if (input.properties != null) output.properties = input.properties;
    return output;
  }

  function quantizeArc(input) {
    var i = 0, j = 1, n = input.length, p, output = new Array(n); // pessimistic
    output[0] = t(input[0], 0);
    while (++i < n) if ((p = t(input[i], i))[0] || p[1]) output[j++] = p; // non-coincident points
    if (j === 1) output[j++] = [0, 0]; // an arc must have at least two points
    output.length = j;
    return output;
  }

  for (key in inputs) outputs[key] = quantizeGeometry(inputs[key]);

  return {
    type: "Topology",
    bbox: box,
    transform: transform,
    objects: outputs,
    arcs: topology.arcs.map(quantizeArc)
  };
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.topojson.simplify"></a>[function <span class="apidocSignatureSpan">topojson.</span>simplify (topology, minWeight)](#apidoc.element.topojson.simplify)
- description and source-code
```javascript
simplify = function (topology, minWeight) {
  minWeight = minWeight == null ? Number.MIN_VALUE : +minWeight;

  // Remove points whose weight is less than the minimum weight.
  var arcs = topology.arcs.map(function(input) {
    var i = -1,
        j = 0,
        n = input.length,
        output = new Array(n), // pessimistic
        point;

    while (++i < n) {
      if ((point = input[i])[2] >= minWeight) {
        output[j++] = [point[0], point[1]];
      }
    }

    output.length = j;
    return output;
  });

  return {
    type: "Topology",
    transform: topology.transform,
    bbox: topology.bbox,
    objects: topology.objects,
    arcs: arcs
  };
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.topojson.sphericalRingArea"></a>[function <span class="apidocSignatureSpan">topojson.</span>sphericalRingArea (ring, interior)](#apidoc.element.topojson.sphericalRingArea)
- description and source-code
```javascript
function sphericalRingArea(ring, interior) {
  var sum = halfArea(ring, true);
  if (interior) sum *= -1;
  return (sum < 0 ? tau + sum : sum) * 2;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.topojson.sphericalTriangleArea"></a>[function <span class="apidocSignatureSpan">topojson.</span>sphericalTriangleArea (t)](#apidoc.element.topojson.sphericalTriangleArea)
- description and source-code
```javascript
function sphericalTriangleArea(t) {
  var sum = halfArea(t, false);
  return (sum < 0 ? tau + sum : sum) * 2;
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.topojson.topology"></a>[function <span class="apidocSignatureSpan">topojson.</span>topology (objects, quantization)](#apidoc.element.topojson.topology)
- description and source-code
```javascript
topology = function (objects, quantization) {
  var bbox = bounds(objects = geometry(objects)),
      transform = quantization > 0 && bbox && prequantize(objects, bbox, quantization),
      topology = dedup(cut(extract(objects))),
      coordinates = topology.coordinates,
      indexByArc = hashmap(topology.arcs.length * 1.4, hashArc, equalArc);

  objects = topology.objects; // for garbage collection
  topology.bbox = bbox;
  topology.arcs = topology.arcs.map(function(arc, i) {
    indexByArc.set(arc, i);
    return coordinates.slice(arc[0], arc[1] + 1);
  });

  delete topology.coordinates;
  coordinates = null;

  function indexGeometry(geometry$$1) {
    if (geometry$$1 && indexGeometryType.hasOwnProperty(geometry$$1.type)) indexGeometryType[geometry$$1.type](geometry$$1);
  }

  var indexGeometryType = {
    GeometryCollection: function(o) { o.geometries.forEach(indexGeometry); },
    LineString: function(o) { o.arcs = indexArcs(o.arcs); },
    MultiLineString: function(o) { o.arcs = o.arcs.map(indexArcs); },
    Polygon: function(o) { o.arcs = o.arcs.map(indexArcs); },
    MultiPolygon: function(o) { o.arcs = o.arcs.map(indexMultiArcs); }
  };

  function indexArcs(arc) {
    var indexes = [];
    do {
      var index = indexByArc.get(arc);
      indexes.push(arc[0] < arc[1] ? index : ~index);
    } while (arc = arc.next);
    return indexes;
  }

  function indexMultiArcs(arcs) {
    return arcs.map(indexArcs);
  }

  for (var key in objects) {
    indexGeometry(objects[key]);
  }

  if (transform) {
    topology.transform = transform;
    topology.arcs = delta(topology.arcs);
  }

  return topology;
}
```
- example usage
```shell
...

If you use NPM, 'npm install topojson'. Otherwise, download the [latest release](https://github.com/topojson/topojson/releases/latest
). You can also load directly from [d3js.org](https://d3js.org) as a [standalone library](https://unpkg.com/topojson@3). AMD, CommonJS
, and vanilla environments are supported. In vanilla, a 'topojson' global is exported:

'''html
<script src="https://unpkg.com/topojson@3"></script>
<script>

var topology = topojson.topology({foo: geojson});

</script>
'''

[Try topojson in your browser.](https://tonicdev.com/npm/topojson)

## API Reference
...
```

#### <a name="apidoc.element.topojson.transform"></a>[function <span class="apidocSignatureSpan">topojson.</span>transform (transform)](#apidoc.element.topojson.transform)
- description and source-code
```javascript
transform = function (transform) {
  if (transform == null) return identity;
  var x0,
      y0,
      kx = transform.scale[0],
      ky = transform.scale[1],
      dx = transform.translate[0],
      dy = transform.translate[1];
  return function(input, i) {
    if (!i) x0 = y0 = 0;
    var j = 2, n = input.length, output = new Array(n);
    output[0] = (x0 += input[0]) * kx + dx;
    output[1] = (y0 += input[1]) * ky + dy;
    while (j < n) output[j] = input[j], ++j;
    return output;
  };
}
```
- example usage
```shell
n/a
```

#### <a name="apidoc.element.topojson.untransform"></a>[function <span class="apidocSignatureSpan">topojson.</span>untransform (transform)](#apidoc.element.topojson.untransform)
- description and source-code
```javascript
untransform = function (transform) {
  if (transform == null) return identity;
  var x0,
      y0,
      kx = transform.scale[0],
      ky = transform.scale[1],
      dx = transform.translate[0],
      dy = transform.translate[1];
  return function(input, i) {
    if (!i) x0 = y0 = 0;
    var j = 2,
        n = input.length,
        output = new Array(n),
        x1 = Math.round((input[0] - dx) / kx),
        y1 = Math.round((input[1] - dy) / ky);
    output[0] = x1 - x0, x0 = x1;
    output[1] = y1 - y0, y0 = y1;
    while (j < n) output[j] = input[j], ++j;
    return output;
  };
}
```
- example usage
```shell
n/a
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
