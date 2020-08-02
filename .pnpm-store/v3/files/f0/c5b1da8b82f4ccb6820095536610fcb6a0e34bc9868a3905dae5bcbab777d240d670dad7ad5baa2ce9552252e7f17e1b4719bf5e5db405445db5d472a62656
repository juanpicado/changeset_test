'use strict';

Object.defineProperty(exports, '__esModule', { value: true });

var babel = require('@babel/core');
var terser = require('terser');

function transformBabel(code, options) {
  options = JSON.parse(options);
  return babel.transformAsync(code, options).then(res => {
    let {
      code,
      map
    } = res;
    return {
      code,
      map
    };
  });
}
function transformTerser(code, optionsString) {
  const options = JSON.parse(optionsString);
  const result = terser.minify(code, options);

  if (result.error) {
    return Promise.reject(result.error);
  } else {
    return Promise.resolve({
      code: result.code,
      map: result.map
    });
  }
}

exports.transformBabel = transformBabel;
exports.transformTerser = transformTerser;
