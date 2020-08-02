"use strict";

Object.defineProperty(exports, "__esModule", {
  value: !0
});

var babel = require("@babel/core"), terser = require("terser");

function transformBabel(code, options) {
  return options = JSON.parse(options), babel.transformAsync(code, options).then(res => {
    let {code: code, map: map} = res;
    return {
      code: code,
      map: map
    };
  });
}

function transformTerser(code, optionsString) {
  const options = JSON.parse(optionsString), result = terser.minify(code, options);
  return result.error ? Promise.reject(result.error) : Promise.resolve({
    code: result.code,
    map: result.map
  });
}

exports.transformBabel = transformBabel, exports.transformTerser = transformTerser;
