.. py:module:: PIL.ImageGrab
.. py:currentmodule:: PIL.ImageGrab

:py:mod:`ImageGrab` Module (macOS and Windows only)
===================================================

The :py:mod:`ImageGrab` module can be used to copy the contents of the screen
or the clipboard to a PIL image memory.

.. note:: The current version works on macOS and Windows only.

.. versionadded:: 1.1.3

.. py:function:: PIL.ImageGrab.grab(bbox=None, include_layered_windows=False, all_screens=False)

    Take a snapshot of the screen. The pixels inside the bounding box are
    returned as an "RGB" image on Windows or "RGBA" on macOS.
    If the bounding box is omitted, the entire screen is copied.

    .. versionadded:: 1.1.3 (Windows), 3.0.0 (macOS)

    :param bbox: What region to copy. Default is the entire screen.
                 Note that on Windows OS, the top-left point may be negative if ``all_screens=True`` is used.
    :param include_layered_windows: Includes layered windows. Windows OS only.

        .. versionadded:: 6.1.0
    :param all_screens: Capture all monitors. Windows OS only.

        .. versionadded:: 6.2.0
    :return: An image

.. py:function:: PIL.ImageGrab.grabclipboard()

    Take a snapshot of the clipboard image, if any.

    .. versionadded:: 1.1.4 (Windows), 3.3.0 (macOS)

    :return: On Windows, an image, a list of filenames,
             or None if the clipboard does not contain image data or filenames.
             Note that if a list is returned, the filenames may not represent image files.

             On Mac, an image,
             or None if the clipboard does not contain image data.
